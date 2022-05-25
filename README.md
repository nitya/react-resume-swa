# Build a Resume with React and Static Web Apps

## Objectives

 * Build a resume with React
 * Deploy the resume to Static Web Apps
 * Dive into the code and see how it works
 * Refactor code for API
 * Customize contents for Resume

---

## 1. Scaffold it
---

### 1.1 Create-React-App

Follow [this tutorial](https://create-react-app.dev/docs/getting-started) for a basic React app. This is one of the most common ways to create your basic React app and see that it works.

```
npx create-react-app my-resume
```

The output will end something like this:

```
...
...
Success! Created my-resume at /Users/nitya/Documents/GitHub/nitya/react-resume-swa/my-resume
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd my-resume
  npm start
```

---

### 1.2. Preview This App

So let's do that and see what the default app looks like:

```
cd my-resume
npm start

...
Starting the Development Server
Compiled successfully!

You can now view my-resume in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://192.168.86.244:3000

Note that the development build is not optimized.
To create a production build, use npm run build.

webpack compiled successfully
```

`🏁 #1` | **This is what you get**

![](./img/01-init-preview.png)


---

## 2. Deploy to Static Web Apps

---

We'll follow [this tutorial](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=react) which shows you how to use the [Azure Static Web Apps Visual Studio Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestaticwebapps) to deploy _any_ React app to Azure. 

 * **This is an IDE-based approach** where you can do all your work in one place - in this case, inside Visual Studio Code (IDE). This is the approach we're taking today.
 * **You may prefer a CLI-based approach** where you do everything with the command-line. The new [Azure Static Web Apps CLI](aka.ms/swa/cli-local-development) is a good option here - we may look at that later.

---

### 2.1 Install the VS Code Extension

If you are already a VS Code user, there are a couple of ways to do this. 

 * Install it from inside VS Code [as described here](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=react#install-azure-static-web-apps-extension) OR
 * Visit the [extension website](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestaticwebapps) and click `Install`- it should automatically launch VS Code for you and complete that workflow.

I've already installed this in the past, so when I take option 1 above - it launches VS Code to **this page** and shows me that the extension is active.

![](./img/02-install-extension.png)

Want to learn more about how you can develop/debug Azure Static Web Apps with VS Code? [Read this article](https://www.azurestaticwebapps.dev/blog/devtools-vscode) fron the #30DaysOfSWA series.

---

## 3. Customize to a Resume Format

For a quick demo, I simply searched [npm](https://www.npmjs.com/) for any pre-existing React component packages that could support building a resume. Here are a few:
 * [React CV](https://www.npmjs.com/package/mark-react-cv) for a customizable and printable 1-page CV.
 * [React CV Builder](https://www.npmjs.com/package/react-cv-builder) for a more componentized version

To keep it simple, let's try the first one.

### 3.1 Add Dependency

For now I'll use the `--legacy-peer-deps` to get around some dependency issues for that package given latest React versions.


```
cd my-resume
npm install react-cv --save --legacy-peer-deps
```

### 3.1 Basic Usage

Followed the [basic usage](https://www.npmjs.com/package/mark-react-cv) guidelines in the npm documentation - except I used the [more detailed format](https://github.com/sbayd/react-cv/blob/master/example/src/data.js) to get the full-resume effect. I did minimal customization of the data - then tried it on my local dev server:


![](./img/03-ada-resume.png)

Let's commit it and see what happens to the hosted version!
