---
title: Login to IDEs and CLIs
slug: login-to-clients
author: Brady
lastModified: 2020-05-25 10:58:57
pubDate: 2020-05-25 10:58:57
categories: Setup
description: In this step, you'll log into your Azure subscription and GitHub accounts everywhere.
phase: 1
step: 3
---

We'll be using a few online services, so it'll be good to use one browser with multiple tabs throughout this workshop. Get started by logging into all of the appropriate sites:

1. [GitHub](https://github.com)
1. The [Azure Portal](https://portal.azure.com)

## Authenticate your environment to GitHub

Once you've logged into these sites, get your local instance of Git configured so you're ready to commit code to GitHub. You can learn about [connecting to GitHub using SSH](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh), or you can use the integrated authentication experience in Visual Studio Code.

## Login to Azure via the Azure CLI

Make sure you have the browser with the Azure account you wish to use highlighted. Then, open a terminal (which ever terminal you choose to use), and invoke the Azure CLI login command by typing the following terminal command:

```bash
az login
```

> **Note**: While the Azure PowerShell Cmdlets are great, we'll be using the Azure CLI exclusively in this workshop. If you're familiar with both and want to use the Azure PowerShell Cmdlets, feel free, but the presenters may not be as familiar with Azure PowerShell as they are the Azure CLI.

A web browser should open up and present you with a success message that you've been logged into the Azure CLI. If you're new to the CLI, the redirection page&mdash;or the [Azure CLI docs start page](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)&mdash;is quite helpful for learning new commands and may be a good bookmark.

![CLI Login](media/cli-login.png)

### Multiple Azure subscriptions

Many folks have multiple Azure subscriptions associated with their login. These subscriptions may be from other workshops, work, or any of a variety of reasons. When you logged in to the CLI, you may have seen JSON output containing the list of subscriptions you can access via the CLI.

If you're unsure which one you want to use, you can see a list of all your subscriptions by using the `az account` command. Showing the result as a table makes it a bit easier to see in the terminal window.

```bash
az account list -o table
```

Once you see the list of subscriptions, you can select the one you want to use for the workshop by once again using the `az account` command:

```bash
az account set -s <your-subscription-guid>
```

## Log in to Azure in Visual Studio Code

Open Visual Studio Code, and open the command palette using <kbd>⌘</kbd>-<kbd>Shift</kbd>-<kbd>P</kbd> or <kbd>Ctrl</kbd>-<kbd>Shift</kbd>-<kbd>P</kbd>. Type the phrase **Sign in** and select the **Azure: Sign in** option.

![CLI Login](media/vs-code-login.png)

Visual Studio Code will launch a web browser and you'll be authenticated to your Microsoft tenant and logged into your Azure subscription. Once you're presented with the login screen you can go back to Visual Studio Code.

![CLI Login](media/vs-code-auth.png)

Use the command palette in Visual Studio Code again to find the **Azure: Select Subscriptions** command.

![CLI Login](media/vs-code-azure-sub.png)

Select the subscription you plan on using for the workshop, and click OK. Now, any of the Visual Studio Code extensions for Azure will have access to the resources in your subscription.

> **Note**: When you're using the integrated terminal in Visual Studio Code, and you're logged into a different account, the terminal takes priority and overrides the Visual Studio Code extensions for Azure. It's therefore important to note that your Azure CLI terminal and Visual Studio Code extensions for Azure will all be using the same subscription.
