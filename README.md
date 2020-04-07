## How to configure

Stack We Used
1. React Js and React Router Dom 
2. HTML5

Folder Structure
1) components
2) themes
3) routers

## components

If you are familiar with react or create react app architecture, then we are familiar with components. Components are reusable codes that you will use throughout your project. Here under components folder, we wrote all of our components individually. We have written these components to make the developer’s life easy. By using these basic components, For example in our components dir there is HeroSection folder whrere we wrote our different styled HeroSection.
For example

```text

└── Src
    ├── components
        ├── Accounts
            └── Forgot.js
            └── .....
            └── Signup.js (code for account signup style)
        ├── Blogs
            └── Blog.js
            └── BlogDetails.js
            └── .....
            └── Sidebar.js (code for sidebar style)
            
        ├── .........
        
        ├── HeaderSection
          └── Header.js (here we wrote all the code for header)
              (we have six different style for hero section and we made component for every single style)
        ├── HeroSection
            └── HeroOne.js (code for hero one style)
            └── HeroTwo.js
            └── .....
            └── HeroSix.js (code for hero six style)
                you can write custom components according to your need.
```

## themes
Under themes dir we wrote all of our root theme like ThemeOne, ThemeTwo where we combined all of our components as per our theme design.
```text
└── Src
    ├── themes
        └── theme-one.js
        └── theme-two.js
        └── ......
        └── theme-six.js
```
```js
For example -- here is the combination to build ThemeOne
```text
└── Src
    ├── themes
        └── theme-one.js
```

```js
<div>
    <Preloader />
    {/*====== Scroll To Top Area Start ======*/}
    <div id="scrollUp" title="Scroll To Top">
        <i className="fas fa-arrow-up" />
    </div>
    {/*====== Scroll To Top Area End ======*/}
    <div className="main">
        <Header imageData={"/img/logo-white.png"} />
        <HeroSection />
        .....
        <FooterSection />
    </div>
</div>
```
Now if you want to make a theme as your default theme as per your requirements, just import the theme on `app.js` and render it like..
```js
import ThemeOne from "./themes/theme-one";

function App() {
  return (
    <div>
      <ThemeOne />
    </div>
  );
}
```

## routers
In router section we used route js. Where we linked all the route for our all theme. For routing we used react-router-dom.

```text

└── Src
    ├── routers
        └── routs.js
```
To view theme-two use with your root url
```text
/theme-two 
```

## theme installtion
To install the theme you have to install [react](https://create-react-app.dev/) than go to the theme root dir where `package.json` located and use
```bash
npm install
```
it will install the packages.

After install process now you can run local server- local server port is 'http://localhost:3000' For developement start use
```bash
npm start
```
## Build your theme
```bash
npm run build
```

## For deployment -- static server
First install
```bash
npm install -g serve
serve -s build
```
If you want to know more about static deployment please visit [Create react app deployment](https://create-react-app.dev/docs/deployment)

Enjoy your theme :)
