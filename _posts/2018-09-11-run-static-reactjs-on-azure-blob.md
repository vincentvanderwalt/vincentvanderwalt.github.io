---
layout: post
title: How to run a static ReactJS site on Azure Blob
subtitle: Shows how to host a React website on azure blob storage
tags: [ReactJS,Hosting,Azure,Blob Storage]
---

Do you always need a full blown web server to host a React based website ?

In this post I'll show you how easy it is to host a static ReactJS based website on Azure blob storage.

# Create a ReactJS site locally

For ease of use we'll utilise the CRA (Create React App) template from facebook. You can find more information about it [Here](https://github.com/facebook/create-react-app).

It's great because it's easy to create a static site using npm build.

I find using the npm package easy to use. I installed it globally by using this command.

```bash
npm i create-react-app -g
```

Now we can go-ahead and create the application.

```bash
npx create-react-app test-app
```

You should see output similar to this

![app creation output](/img/static-reactjs-site/create_app_output.PNG)

Now navigate to the created app folder

```bash
cd test-app
```

Use npm to start the application

```bash
npm start
```

The site will start and open a web browser. The site will look similar to this

![running test app](/img/static-reactjs-site/running_app.PNG)

# Build a static production version

To deploy the site you need the production version of the site.

Run the following command in the root of the application

```bash
npm run build
```

this creates a static site under the /build folder

![build output folder](/img/static-reactjs-site/build_folder.PNG)

To test the build locally, in the root of the application, run the following command

```bash
serve -s build
```

# Deploy to Azure Blob storage

Now we deploy the site

Navigate to your Azure portal and select **Create a resource**

![new resource](/img/static-reactjs-site/create_resource.PNG)

Search for **Storage Account**

![new storage account](/img/static-reactjs-site/new_storage_account.PNG)

click **Create**

Add a name and resource group for your storage account and click **create**

![storage details](/img/static-reactjs-site/storage_details.PNG)

Once the storage account is running, select the **Static website** option

![static website option](/img/static-reactjs-site/static_website_option.PNG)

Select the **Enable** option and add **index.html** as the Index document name

![static website data](/img/static-reactjs-site/static_website_data.PNG)

Click **Save**

Notice how azure has created a container called **$web**, This is where you'll be copying your site to.

Also notice the url of your static site.

![static storage data](/img/static-reactjs-site/static_storage_data.PNG)

Now copy your **build folder** contents to the $web container

![build output folder](/img/static-reactjs-site/build_folder.PNG)

I'm using the excellent / free tool called **Cloudberry Explorer for Azure Blob Storage** to copy data to Azure. More details can be found [Here](https://www.cloudberrylab.com/explorer/microsoft-azure.aspx)

![Cloudberry](/img/static-reactjs-site/cloud_berry.PNG)

You should see the site running on the Url provided under the *static website option*

![hosted website](/img/static-reactjs-site/hosted_website.PNG)