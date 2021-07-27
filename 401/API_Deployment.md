# Configuring Django Settings

Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

Sharing settings between team members. You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

## Setting Configuration: Different Approaches
There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best. Let’s take a brief look at the most popular ones to examine their weaknesses and strengths.

## settings_local.py

This is the oldest method. I used it when I was configuring a Django project on a production server for the first time. I saw a lot of people use it back in the day, and I still see it now.

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.

# How Does SSH Work
## What is SSH

SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet. The service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner. It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.

The Figure Below shows a typical SSH Window. Any Linux or macOS user can SSH into their remote server directly from the terminal window. Windows users can take advantage of SSH clients like Putty.  You can execute shell commands in the same manner as you would if you were physically operating the remote computer.

![0](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/shell-snapshot.jpg)

This SSH tutorial will cover the basics of how does ssh work, along with the underlying technologies used by the protocol to offer a secured method of remote access. It will cover the different layers and types of encryption used, along with the purpose of each layer.

## How Does SSH Work

If you’re using Linux or Mac, then using SSH is very simple. If you use Windows, you will need to utilize an SSH client to open SSH connections. The most popular SSH client is PuTTY, which you can learn more about here.

For Mac and Linux users, head over to your terminal program and then follow the procedure below:

The SSH command consists of 3 distinct parts:

```
ssh {user}@{host}
```

The SSH key command instructs your system that you want to open an encrypted Secure Shell Connection. {user} represents the account you want to access. For example, you may want to access the root user, which is basically synonymous for system administrator with complete rights to modify anything on the system. {host} refers to the computer you want to access. This can be an IP Address (e.g. 244.235.23.19) or a domain name (e.g. www.xyzdomain.com).

When you hit enter, you will be prompted to enter the password for the requested account. When you type it in, nothing will appear on the screen, but your password is, in fact being transmitted. Once you’re done typing, hit enter once again. If your password is correct, you will be greeted with a remote terminal window.

## Understanding Different Encryption Techniques

The significant advantage offered by SSH over its predecessors is the use of encryption to ensure secure transfer of information between the host and the client. Host refers to the remote server you are trying to access, while the client is the computer you are using to access the host. There are three different encryption technologies used by SSH:

1. Symmetrical encryption
2. Asymmetrical encryption
3. Hashing.

## Symmetric Encryption

Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Effectively, any one possessing the key can decrypt the message being transferred.

![1](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.jpg)

Symmetrical encryption is often called shared key or shared secret encryption. There is usually only one key that is used, or sometimes a pair keys where one key can easily be calculated using the other key.

Symmetric keys are used to encrypt the entire communication during a SSH Session. Both the client and the server derive the secret key using an agreed method, and the resultant key is never disclosed to any third party. The process of creating a symmetric key is carried out by a key exchange algorithm. What makes this algorithm particularly secure is the fact that the key is never transmitted between the client and the host. Instead, the two computers share public pieces of data and then manipulate it to independently calculate the secret key. Even if another machine captures the publically shared data, it won’t be able to calculate the key because the key exchange algorithm is not known.

It must be noted, however, that the secret token is specific to each SSH session, and is generated prior to client authentication. Once the key has been generated, all packets moving between the two machines must be encrypted by the private key. This includes the password typed into the console by the user, so credentials are always protected from network packet sniffers.

A variety of symmetrical encryption ciphers exist, including, but not limited to, AES (Advanced Encryption Standard), CAST128, Blowfish etc. Before establishing a secured connection, the client and a host decide upon which cipher to use, by publishing a list of supported cyphers in order of preference. The most preferred cypher from the clients supported cyphers that is present on the host’s list is used as the bidirectional cypher.

