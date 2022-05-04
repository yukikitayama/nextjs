# Demo NextJS Amplify

This repo studies how to deploy NextJS app in AWS Amplify by enabling server-side rendering. Find detail at [Host a Next.js SSR app with real-time data on AWS Amplify](https://aws.amazon.com/blogs/mobile/host-a-next-js-ssr-app-with-real-time-data-on-aws-amplify/)

## Concept

- Server-rendered pages or API routes get deployed in your account as `Lambda@Edge` functions served via `CloudFront`.
  - After deployment in Amplify, check log of Deploy step, and see `SSR` and `API` has `Lambda@Edge` with IDs.
- `api` in `pages` folder can be also accessible by `AMPLIFY_DOMAIN_NAME/api/ENDPOINT`.

## Benefit to Use Amplify to Host NextJS

- When connecting GitHub repository, Amplify will see the project configuration and automatically detect that your app is an SSR app.

## How to Allow Amplify to Host NextJS

1. AWS console
2. AWS amplify
3. all apps
4. New app
5. Host web app
6. GitHub
7. Select NextJS project in GitHub
8. Select or Create a role with Amplify Hosting permissions

## Deployment

- Just commit the code to GitHub, and Amplify will automatically start deployment
- No need to `$ npm run build`.

## Connect NextJS app to Amplify backend

- Run the following in the terminal of the NextJS project folder
  - `$ amplify pull --appId SOME_ID --envName SOME_ENV`
    - This can omit `$ amplify init`
  - ID and environment are found in AWS Amplify console Backend environments tab.

## Resouce

- [Hosting Next.js](https://docs.amplify.aws/guides/hosting/nextjs/q/platform/js/)
  - This instruction was stable.
- [SSR Support for AWS Amplify JavaScript Libraries](https://aws.amazon.com/blogs/mobile/ssr-support-for-aws-amplify-javascript-libraries/)