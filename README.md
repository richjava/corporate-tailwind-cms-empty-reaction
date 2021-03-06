# Built.js Strapi CMS
Strapi content management system, generated by Built.js. 

## How to run locally
1. Install the dependencies:
```
npm i
```
2. Run the app in develop mode:
```
npm run develop
```

## How to deploy to CodeSandbox

1. Click this button:

[![Deploy to CodeSandbox](/setup/lib/codesandbox-btn.png "Deploy to CodeSandbox")](https://codesandbox.io/s/github/<github-username>/<github-project-name>)

2. You'll be directed to CodeSandbox. Once you're in the project editor, go to "Server Control Panel (in the left sidenav) > Secret Keys". Enter "ADMIN_JWT_SECRET" into the "Name" field, and a secret value for the "Value" field", and then click the "Add Secret" button.

3. Wait for project to build. If you see a "502: Bad Gateway" message in the browser preview, ignore it. Wait until you see the "Opening the admin panel..." message in the terminal. In a new browser window, go to the url you see in the browser preview address bar, e.g:
```https://<project-name>.sse.codesandbox.io```

4. Go to the Strapi Admin page and register as a new user.

## How to link your Strapi CMS on CodeSandbox to your frontend Next.JS project on Vercel
1. On Vercel, add an Environment Variable to tell the frontend project to use data from the Strapi CMS: 
- On the Environment Variables page of your Project Settings, enter ```API_URL``` for the Name for your Environment Variable.
- Paste in the URL for your CodeSandbox Strapi CMS (e.g. https://abc123.sse.codesandbox.io).
- Leave all Environment checkboxes checked.
- Click the "Add" button.

You can then configure which Environments this variable should apply to.

Finally, click Save.

2. On Vercel, create a Deploy Hook:
- Navigate to the project overview and go to Settings > Git > Deploy Hooks.
- Add a hook name and which git branch you want to use, e.g. Hook Name: Strapi, Git Branch Name: main, then click the "Create Hook" button.
- Copy the URL of the webhook.

2. On CodeSandbox: 
- Log into the Strapi Admin and navigate to Settings > Webhooks, then click "Add New Webhook".
- Fill in the name (e.g. Trigger Vercel Deployment), paste in the URL you copied from Vercel in the first step, and choose which events you'd like to trigger a re-build of the frontend website.
- Click the "Save" button and then test using the Trigger button at the top. If you navigage back to the project on Vercel, you should see a new build in progress. This should now happen every time you update content in your CMS, and the changes should be able to see the changes in your site once the Vercel project has finished building.
