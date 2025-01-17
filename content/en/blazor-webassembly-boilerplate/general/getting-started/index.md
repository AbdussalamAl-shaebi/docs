---
title: "Getting Started 🚀"
description: "Getting Started with fullstackhero's Blazor WebAssembly Boilerplate."
lead: "Getting Started with fullstackhero's Blazor WebAssembly Boilerplate."
date: 2021-08-24T11:40:05+05:30
lastmod: 2021-11-28T17:35:38+05:30
draft: false
images: []
menu:
  blazor-webassembly-boilerplate:
    identifier: "general-getting-started"
    name: "Getting Started 🚀"
    parent: "general"
weight: 3
toc: true
---

Firstly, make sure that you have already setup your development environment that runs the prerequisite tools and SDKs. Refer [Development Environment](/blazor-webassembly-boilerplate/general/development-environment/) for details.


To get started with this Boilerplate, here are the avaiable options.

- Fork the Repository. Use this if you want to always keep your version of the Boilerplate up-to date with the latest changes.
- Install using dotnet new . Use this for release versions of the Boilerplate only. Note that this option is currently unavailable for Blazor WASM Boilerplate.

## Forking the Repository

You would probably need to take this approach if you want to keep your source code upto date with the latest changes. To get started based on this repository, you need to get a copy locally. You have three options: fork, clone, or download.

- Make a fork of fullstackhero's `blazor-wasm-boilerplate` repository in your Github account.
- Next, since you need to start your private personal project, create your new `blazor-wasm-boilerplate` personal project by cloning the forked repository on your personal github. This could be done as simple as running `git clone https://github.com/{yourgithubuseraccount}/blazor-wasm-boilerplate.git` locally on your development machine.
- Setup an upstream remote on your personal project pointing to your forked repository using command `git remote add upstream https://github.com/{yourgithubuseraccount}/blazor-wasm-boilerplate` and `git remote set-url --push upstream DISABLE`

Now, whenever there is a new update on fullstackhero's `blazor-wasm-boilerplate` repository, you could simply pull in the latest change on your private fork of the fullstackhero's `blazor-wasm-boilerplate` repository and later merge these changes with you personal projects.

For step by step instructions, [follow this](https://discord.com/channels/878181478972928011/892573122186838046/933513103688224838) and [this](https://gist.github.com/0xjac/85097472043b697ab57ba1b1c7530274).

## Installing NuGet Package

This is by far the easiest and the most streamlined way of getting the latest available `Release version` of fullstackhero Blazor WebAssembly Boilerplate.

Open up your Command Prompt / Powershell and run the following command to install the solution template.

```powershell
dotnet new --install FullStackHero.BlazorWebAssembly.Boilerplate
```
or, if you want to use a specific version of the boilerplate, use

```powershell
dotnet new --install FullStackHero.BlazorWebAssembly.Boilerplate::0.0.1-rc
```
This would install the `fullstackhero Blazor WebAssembly Boilerplate` template globally on your machine. Do note that, at the time of writing this documentation, the latest available version is **0.0.1-rc** which is also one of the first stable pre-release version of the package. It is highly likely that there is already a newer version available when you are reading this.

> *To get the latest version of the package, visit [nuget.org](https://www.nuget.org/packages/FullStackHero.BlazorWebAssembly.Boilerplate/)*
>
> *FullStackHero.BlazorWebAssembly.Boilerplate is now in pre-release state. You can find the latest version on NuGet.org*

{{< alert text="FullStackHero.BlazorWebAssembly.Boilerplate::0.0.1-rc is compatible only with FullStackHero.WebAPI.Boilerplate::0.0.6-rc and above." />}}



Get the .NET WebApi Boilerplate by running the following command

```
dotnet new --install FullStackHero.WebAPI.Boilerplate::0.0.6-rc
```

### Creating your First Solution

> Note that this is not valid only if you have installed the NuGet package of this Boilerplate.

Now that you have installed the template locally on your machine, let's see how you can start generating Blazor Web Assembly Projects.

Simply navigate to a new directory (wherever you want to place your new solution at), and open up Command Prompt at the opened directory.

Run the following command. Note that, in this demonstration I am naming my new solution as `FSH.Blazor`.

```powershell
dotnet new fsh-blazor -o FSH.Blazor
```

Once that is done, your new solution is created for you. As simple as that!

## Running the Application

Firstly, keep in mind that this is a client application that actually consumes data by sending HTTP Requests to the API Server. Thus, you need to make sure that the API is up and running.

To learn about setting up the API Server, refer [Getting Started with fullstackhero's .NET Web API](/dotnet-webapi-boilerplate/general/getting-started/).

Once the Server is up and running, like any other Blazor application, simply navigate to the Host folder under the source folder of the Blazor Project (`\src\Host`) and run the following standard commands.

- `dotnet restore`
- `dotnet build`
- `dotnet run`

Once the build process is complete, the application would be reachable by accessing `https://localhost:5002` on your browser.

By default, the API Server is set to be running on port 5001 of your local machine. If for some port related reason, you have to run the API on another port or so, navigate to `src\Client\wwwroot\appsettings.json` of the Blazor Project and change the API Base URL Property and set the value to the port that's exposing the API. This is the default configuration `"ApiBaseUrl": "https://localhost:5001/"`.

Simalarly, the Blazor Project by default is set to run on port 5003 of your local machine. Incase you change this to something else, ensure that you have updated the cors.json configuration file on your API project. This makes sure that there is no CORS related issues while the Blazor project tries to access the API Endpoints.
