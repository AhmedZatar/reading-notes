# Dynamic Routes

## Page Path Depends on External Data

![0](https://nextjs.org/static/images/learn/dynamic-routes/page-path-external-data.png)

### How to Statically Generate Pages with Dynamic Routes

In our case, we want to create dynamic routes for blog posts:

* We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
* Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.


### Here’s a graphic summary of what we just talked about:

![1](https://nextjs.org/static/images/learn/dynamic-routes/how-to-dynamic-routes.png)

### Implement getStaticPaths

First, let’s set up the files:

* Create a file called [id].js inside the pages/posts directory.
* Also, remove first-post.js inside the pages/posts directory — we’ll no longer use this.

Then, open pages/posts/[id].js in your editor and paste the following code. 

```
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
```

Then, open lib/posts.js and add the following getAllPostIds function at the bottom. It will return the list of file names (excluding .md) in the posts directory:

```
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory)

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map(fileName => {
    return {
      params: {
        id: fileName.replace(/\.md$/, '')
      }
    }
  })
}
```

Finally, we'll import the getAllPostIds function and use it inside getStaticPaths. Open pages/posts/[id].js and copy the following code above the exported Post component:

```
import { getAllPostIds } from '../../lib/posts'

export async function getStaticPaths() {
  const paths = getAllPostIds()
  return {
    paths,
    fallback: false
  }
}

```

* paths contains the array of known paths returned by getAllPostIds(), which include the params defined by pages/posts/[id].js. Learn more in the paths key documentation
* Ignore fallback: false for now — we’ll explain that later.


We need to fetch necessary data to render the post with the given id.

To do so, open lib/posts.js again and add the following getPostData function at the bottom. It will return the post data based on id:

```
export function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`)
  const fileContents = fs.readFileSync(fullPath, 'utf8')

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents)

  // Combine the data with the id
  return {
    id,
    ...matterResult.data
  }
}
```

Then, open pages/posts/[id].js and replace this line:

```
import { getAllPostIds } from '../../lib/posts'
```

with the following code:

```
import { getAllPostIds, getPostData } from '../../lib/posts'

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id)
  return {
    props: {
      postData
    }
  }
}
```

The post page is now using the getPostData function in getStaticProps to get the post data and return it as props.

Now, let's update the Post component to use postData. In pages/posts/[id].js replace the exported Post component with the following code:

```
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
    </Layout>
  )
}
```

# Deploying Your Next.js App


## Push to GitHub

## Deploy to Vercel

The easiest way to deploy Next.js to production is to use the Vercel platform developed by the creators of Next.js.

Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database. We make it easy for frontend teams to develop, preview, and ship delightful user experiences, where performance is the default. You can start using it for free — no credit card required.

### Create a Vercel Account

First, go to https://vercel.com/signup to create a Vercel account. Choose Continue with GitHub and go through the sign up process.

### Import your nextjs-blog repository

Once you’re signed up, import your nextjs-blog repository on Vercel. You can do so from here: https://vercel.com/import/git.

* You’ll need to Install Vercel for GitHub. You can give it access to All Repositories.
* Once you’ve installed Vercel, import nextjs-blog.

You can use default values for the following settings — no need to change anything. Vercel automatically detects that you have a Next.js app and chooses optimal build settings for you.

* Project Name
* Root Directory
* Build Command
* Output Directory
* Development Command

When you deploy, your Next.js app will start building. It should finish in under a minute.

## Next.js and Vercel
Vercel is made by the creators of Next.js and has first-class support for Next.js. When you deploy your Next.js app to Vercel, the following happens by default:

* Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from the Vercel Edge Network, which is blazingly fast.
* Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.

Vercel has many more features, such as:

* Custom Domains: Once deployed on Vercel, you can assign a custom domain to your Next.js app. Take a look at our documentation here.
* Environment Variables: You can also set environment variables on Vercel. Take a look at our documentation here. You can then use those environment variables in your Next.js app.
* Automatic HTTPS: HTTPS is enabled by default (including custom domains) and doesn't require extra configuration. We auto-renew SSL certificates.