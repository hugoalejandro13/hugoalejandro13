---
layout: "post"
title: "Doing more with Vuetify"
---

On my last blog entry about Vuetify, I mentioned the amazing documentation that is available from Vuetify's Webpage (I said there was a lot of really cool stuff in there, and there really is). You can go ahead and take a look at all the different documentation by clicking [here.](https://vuetifyjs.com/en/getting-started/quick-start/ "Vuetify Documentation")

As also mentioned in my last post, I will be utilizing Visual Studio Code as my IDE of choice. You can go ahead and download that by clicking [here.](https://code.visualstudio.com/)

In this post, I'll be highlighting some of my favorite bits I've learned so far while using Vuetify by disecting a current Vuetify projevt that I'm working on. Feel free to click on whichever section you'd like if you're interested!

One of my favorite features so far of Vuetify is the ability to have certain components accross any webpages that you design. This is particularly useful for components such as a navigation bar, for example. Below is an example of the functions of a Navbar, as well as a Drawer for site navigation.

![image](hugoalejandro13/images/blog9/first.gif)

In order to achieve this, there are two components that are utilized; [v-app-bar](https://vuetifyjs.com/en/components/app-bars/) and [v-navigation-drawer](https://vuetifyjs.com/en/components/navigation-drawers/). These both work really well together

The code to make this navigation bar and drawer clickable is down below:

![image](hugoalejandro13/images/blog9/image1.PNG)

<v-app-bar> is the component for the nav bar. You can set the preffered color utilizing a color code.

<v-app-bar-nav-icon> is the component for the clickable icon. Most importantly, @click="drawer = !drawer" will change the boolean value of drawer. Not adding this would leave the drawer, as opposed to closing with each click. We'll touch on that a bit later.

<v-img> is the component for the image that is displayed. In this case, it is the CSUN logo. The image source is indicated, as well as the "shrink mr-2" class. Shrink will shrink the image dependant on the size of the window. "m" stands for margin, "r" stands for right, and the "-2" is the number of pixels. Vueitfy does so in increments of 4, so 2 would actually be 8 pixels. The transition value will let vuetify know which transition effect to utilize; In this instance, it's the scale-transition. Additionally, there are other vaules set for both height and width.

<v-toolbar-title> will display whatever text you'd like as the title of the Navbar. There really isn't all too much to this particular section. The only additional changes are to the <span> tag for the Senior Design text, which will be slightly thiner than the 2020 text because of class="font-weight-leight"

Now let's move on to the Drawer (the left-side menu of the website).

![image](hugoalejandro13/images/blog9/image2.PNG)

<v-navigation-drawer> is the component for the left-handed navigation panel. The key part here is v-model="drawer", which binds the navigation drawer component to the boolean value of "drawer". We'll touch on that a bit later.

<v-list> creates a list.

<v-list-item> creates a list of items. In this particular case, we have a loop that reads through the links array (I'll show you where we defined this a bit later). Additionally, we have the same @Click="drawer = !drawer" so that any click on a button from the drawer will close it.

<v-list-item-action> is something I'll be honest about. I don't really know why this needs to be here, but it works... Haha!

<v-icon> will display an icon for each item listed. v-text="link.icon" will look at each item's icon value, and display that particular icon. We'll touch on the icons in a little bit.

<v-list-item-content> is kinda similar to <v-list-item-action>... only in the sense that I'm not sure why it needs to be there... but it works!

<v-list-item-title> will display the Name, or title, of each item on the list. v-text="link.text" will look at each item's text value, and display that particular icon. We'll touch on the icons in a little bit.

A bit Later

Now, you might be asking yourself, "Hey guy who forgets to do these blogs all the time, you said you'd 'touch on [insert here] a but later'!" Well, here we are a bit Later. So, lets talk about it!

We will be disecting the <script> section of the Navbar component as seen below:

![image](hugoalejandro13/images/blog9/image3.PNG)

drawer: This is the boolean value we had talked about previously. By default, it is set to false. This way, when you load the webpage the drawer is set closed by default.

link: This is the array in which we have differnt values for each clickable item. Each item has various attributes set, such as "icon", "text" and "route". The icon value is the name of the icon that is set for each item. (You can find a full list of available icons [here](https://https://materialdesignicons.com/)). The Text attribute is the text that is displayed on the left-hand drawer. The route is where the specific item will link you to. We'll touch a bit more on routing on my next post regarding vuetify.

That's it for this week's post. Thanks for reading!
