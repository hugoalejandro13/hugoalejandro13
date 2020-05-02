---
layout: "post"
title: "Building with Vue and AWS"
---

On my last blog entries about Vuetify, I mentioned the amazing documentation that is available from Vuetify's Webpage (I said there was a lot of really cool stuff in there, and there really is). You can go ahead and take a look at all the different documentation by clicking [here.](https://vuetifyjs.com/en/getting-started/quick-start/ "Vuetify Documentation")

As also mentioned in my last post, I will be utilizing Visual Studio Code as my IDE of choice. You can go ahead and download that by clicking [here.](https://code.visualstudio.com/)

One of the hobbies that has helped me keep some resemblence of sanity is Music. I'm a classically trained musician who's had many wonderful experiences by playing the trumpet in an orchestral setting since the third grade. When I began college, I felt that I had no choice but to let that go. However, I've recently began rediscovering my love for music through a Digital Audio Workstation (DAW). One of the things I've been able to do now is create my own music, finally at a level I feel is worth sharing with the world.

In this post, I'll be showing the beginnings of my personal website for my music. I will be combining the skills that I have learned throughout my years in college with my passion for music. Specifically in this blog, I will show how I set myself up to easily deploy my website (build with Vue) onto AWS utilzing AWS Amplify!


## **Setting Up A New Vue Project**

First thing is first, we'll have to set up a new Vue Project! I did this by utilizing the Command line. In this case, I am utilizing windows 10. But depending on which OS you are running, you might be utilizing the terminal.

First I made a new directory named hugoalejandro utilizing the **mkdir** command.

![image](/hugoalejandro13/images/blog12/image1.png)

Then switched into it utilizing the **cd** command.
![image](/hugoalejandro13/images/blog12/image2.png)

This is the directory I decided to utilize to build my website. My next command was **vue create hugoalejandro** in order to create the Vue project. I went ahead and chose all defauly settings.

![image](/hugoalejandro13/images/blog12/image3.png)

Lastly, I also added the Vuetify as my component framework. I did this by running **vue add vuetify**. I also accepted all the defauly settings.

![image](/hugoalejandro13/images/blog12/image4.png)

## **Setting up AWS Amplify**

In order to Install AWS Amplify, it's just a matter of **npm install -g @aws-amplify/cli**.

![image](/hugoalejandro13/images/blog12/image5.png)

![image](/hugoalejandro13/images/blog12/image6.png)

Now, depending on how fast your computer is, this process might take a little bit. Mine is rather old, so it took a whole 62 seconds! After that now feels like an eternity, you should get the following.

![image](/hugoalejandro13/images/blog12/image6.png)

We're not quite there yet, but we almost are! Next we'll have to run both **npm i aws-amplify** and **npm i aws-amplify-vue**.

![image](/hugoalejandro13/images/blog12/image7.png)

![image](/hugoalejandro13/images/blog12/image8.png)



## **Configuring AWS Amplify**

Next, we'll go ahead and configure AWS Amplify. We start this by typing in **amplify configure**.

Running Amplify Configure will open up our AWS Console on your web browser of choice (Again, it should be Google Chrome!!!). If you are not logged in, it'll prompt you to log in. In my case, I am already logged in.

Next, you'll be prompted to select your current region. You can find this on the upper right corner of your AWS Console.
Select your corresponding one and press enter.

![image](/hugoalejandro13/images/blog12/image9.png)

Next, you'll be prompted to create a new IAM User name. I went ahead and used the default by pressing enter. Doing so will open up the IAM user creation page on your browser once again. Click next on the following two screens, then return to your command line or terminal and click enter.

![image](/hugoalejandro13/images/blog12/image10.png)

Click next on the following two screens, then return to your command line or terminal and click enter.

![image](/hugoalejandro13/images/blog12/image11.png)

After this, you will be prompted to enter both the Access Key ID, as well as the Secret Access Key. **Make sure these stay secret!**




That's it for this week's post. Thanks for reading!
