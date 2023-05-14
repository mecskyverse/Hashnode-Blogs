---
title: "How to use Google Maps API  with Vite React"
datePublished: Sun May 14 2023 16:27:51 GMT+0000 (Coordinated Universal Time)
cuid: clhnmqu8h00000al4axsrcz26
slug: how-to-use-google-maps-api-with-vite-react
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1684081525794/50739452-1d17-4f8c-a5c8-46e20352f6ec.png
tags: apis, reactjs, google-maps, integration, vite

---

Google Maps has become an unavoidable part of our life. From finding your way to explore new places it can do all. Using it on our website can help us to give someone our address, find some places, or calculate the distance in seconds. Google Maps also provides an Embedding feature which can help you to show a small location but if you need to add features of google maps and build your web app on top of it. Then you would be needing Google Maps API support.

## What are we going to build?

We are going to build a simple Google Map Section and a form to select the Destination and Origin of the location. We will integrate the routing functionality to show us the routes between two places and also an autosuggestion input field which will generate suggestions of locations based on our search.

%[https://www.youtube.com/watch?v=jECT7QTEX5o] 

You can watch the video for further details and I will take you through the code part in a later section.

## Setup Vite + React Project

If you wanted to set up the project locally follow the below steps. We are using this [GitHub](https://github.com/mecskyverse/vite-maps-tutorial) repo for further learning of the tutorial. You should know basic react and that's it for following along with this tutorial

```javascript
git clone https://github.com/mecskyverse/vite-maps-tutorial
```

### Setting up Google Cloud Platform for an api key

I would say this can be the toughest part of this tutorial if you are a resident of India. Due to RBI regularities connecting accounts can be cumbersome sometimes but I will show you how you can create an API key. Also, Google Maps API is free to use it gives you $300 credits which can easily be enough for your project.

* Open the [Google Cloud Platform](https://cloud.google.com/) and create or link your Google account to this platform.
    
* Now Click on Console in the top right corner
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684038651409/1b768f5e-a8d3-41db-b049-53794f294ca0.png align="center")
    
* In the Top Left corner you will get Navigation Menu, Home Button and a project selection tab.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684039804451/c0a91af4-a7bd-464a-9f6e-9841fb8e95b7.png align="center")

As per RBI Guidelines, google cloud needs to access your debit or credit card for payments but as I say you will get a free $300 credit. So, it is just a formality for Cloud to get your card details. Now, mainly google cloud platform provides you with two services Google Vms and Google Apis, and for both types of services, we have to link our different cards.

* For our purpose of google maps api go to &gt; Navigation Menu and then select &gt; Billing &gt; Create Account &gt; Select your Country and Add name to the account.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684040608516/f2b5c2e8-e582-4f56-aad2-182b2bb42024.png align="center")

* In the last dropdown menu select Google Maps Platform. Your form will look like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684040831930/ef142852-6c97-4db9-91d8-aee501c13204.png align="center")
    
* Enter Your basic details and add a card preferably Visa or MasterCard and your billing account will be created. If you already have your card linked to the Google Cloud platform then it will not work you have to delete that card from the google cloud platform billing account or add a new card. It took me a whole day to resolve this problem.
    
* If you can successfully submit and verify your card then congrats next steps will be much easier.
    
* Click on the project selection tab in the top left corner and create a new project &gt; Enter the project name you wanted and select the billing account which you have created for google maps.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684041313169/421fca56-b7fa-4fc2-98e2-0afc42b063be.png align="center")
    
* Select your newly build project from the project selection tab and go to API services &gt; Enabled Api & services from the navigation menu.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684041499747/af128bb2-ac65-4e2f-8307-0fb2a1c6b419.png align="center")
    
* Click on Enable APIs and Services &gt; select Maps Javascript API &gt; Enable
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684041541711/73df67c8-2a12-44e9-b9d6-ac87f26c1117.png align="center")
    
* This will enable your API&gt; Go back to Enabled APIs & services &gt; Select Credentials
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684042134194/7f3fc7b4-ffef-4902-85be-6631ad7cd776.png align="center")
    
* Generate your API key and copy it. Now, your work with Google Cloud Platform is ended. Now I will take you through the code part of this project.
    

### Steps to setup locally

we are using the npm package manager you can use yarn and make sure you have node.js installed. I am using NPM version 9.5.1 and Node version 16.14.2 I hope you will not face any problems with your version but in any case, you can use these versions.

```plaintext
git clone https://github.com/mecskyverse/vite-maps-tutorial.git
cd vite-maps-tutorial
npm i
```

This will install all the dependencies you need. Now rename the .env.sample file to the .env file and make sure this file is present in the root directory. Your folder will look like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684038095538/6800cdf0-deb6-450c-8cda-f9837e875e85.png align="center")

* Open .env and paste your API key into it. In your terminal type the below command and go to localhost:5173. You can see your project
    
    ```plaintext
    npm run dev
    ```
    

## Understanding the Code

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684042659755/55b08a1c-d59a-4942-b49a-918f26c3e4b8.png align="center")

Firstly we are importing some hooks from React and then

* useJsApiLoader: to load our google maps through our API in js
    
* GoogleMap: If we want to show Google Maps on our site we will import this component.
    
* Marker: The component is used to mark certain locations on the Map.
    
* AutoComplete: We will wrap our input field in this component so that we can get suggestions for the location we are trying to access.
    
* DirectionsRenderer: This component will help us to generate a path between two locations.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684043314513/6c17eee4-965b-4a84-b51e-79dd705d40b3.png align="center")

Here we are making our functional component and using some state variables to record We also see that we are using the `useRef` hook to create references to the input fields for the source and destination:

We will be using these references to read the values entered by the user and to clear the input fields.

We are also using the `useJsApiLoader` hook to access the Google Maps API through our API key, which is stored in the `.env` file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684078235867/a5ae2b42-fca1-4d30-95d0-66e8aee7e4b1.png align="center")

`calculateRoute`: This function is called when the user submits the source and destination input fields. It first checks if both fields are non-empty, and if so, it creates a new `DirectionsService` object, which is used to calculate the route between the source and destination.

`results` object contains information about the calculated route, including the distance and duration of the route. The `calculateRoute` function then uses the `setDirectionsResponse`, `setDistance`, and `setDuration` functions to update the state variables with the calculated route information.

`clearRoute`: This function is called when the user clicks the "Clear Route" button. It simply resets the state variables to their initial values.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684080309925/b267da47-0bbe-485c-8421-8d7c3ee30df1.png align="center")

The `GoogleMap` component takes in various props to configure the map. The `center` prop specifies the initial center coordinates for the map. In this case, it is set to `center` which is an object with latitude and longitude values for New Delhi, India.

The `zoom` prop specifies the initial zoom level of the map. Here, it is set to 15.

A `mapContainerStyle` prop is an object that specifies the CSS styles for the container of the map.

The `options` prop is an object that specifies various options for the map, such as whether to show the street view control, zoom control, etc.

Inside the `GoogleMap` component, there are two child components.

The first child component is a `Marker` component. It renders a marker at the center coordinates of the map. In this case, it is set to `center`.

The `DirectionsRenderer` component renders the route between the source and destination locations on the map, based on the response received from the Google Maps API

## Conclusion

In conclusion, integrating Google Maps API with Vite React is a straightforward process that can add a lot of value to your applications

If you have any questions or comments, please feel free to reach out to me on Twitter at [**@**](https://twitter.com/yourTwitterHandle)**mecskyverse**. I'm always happy to help and discuss web development!