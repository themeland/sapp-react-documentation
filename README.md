# Template customization


## public
I hope you have seen this template `public` folder on the downloaded package `Sapp - React App Landing Page` from ThemeForest.

In this `public` folder you can see `index.html` file. This file structure is like this-

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!--meta, title, google fonts, all css linking here-->
</head>

<body>

  <div id="root"></div>
 
 <!--all js linking here-->
</body>

</html>
```

All HTML content will be load into this `div`:
```html
<div id="root"></div>
```




## entry points

##### index.js
Template `index.js` structure like this-
```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(<App />, document.getElementById('root'));

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

```

##### app.js
Template `app.js` structure like this-
```js
import React from 'react';

// importing MyRouts where we located all of our theme
import MyRouts from './routers/routs'

function App() {
  return (
    <div>
      <MyRouts />
    </div>
  );
}

export default App;

```


## themes

`themes` folder included on `src` folder. You can check our folder structure on `src` folder menu.
This is `theme` folder structure-
```text
|-- themes
    |-- theme-one.js ( default theme)
    |-- theme-two.js ( demo theme 2)
    .....
    |-- theme-six.js ( demo theme 6 )
```

`theme` folder contains all of our 6 demos.


## components

`components` folder included on `src` folder. This is `components` folder structure-
```text
|-- components
    |-- Accounts
        └── Forgot.js (here we wrote all the code for Forgot Password Page)
        └── Login.js (code for Login Page)
        └── Signup.js (code for Signup Page)
    |-- Blogs
        └── Blog.js (code for blog two column page)
        └── BlogDetails.js (code for blog details page)
        .....
        └── Breadcrumb.js (code for breadcrumb)
        └── Sidebar.js (code for blog sidebar)
        
     .........
     
    |-- HeaderSection
        └── Header.js (here we wrote all the code for header)
        (we have six different style for hero section and we maid component for every single style)
    |-- HeroSection
        └── HeroOne.js (code for hero one style)
        └── HeroTwo.js
        └── .....
        └── HeroSix.js (code for her six style)
            you can write custom components according to your need.
            
     .........
     
     |-- WorkSection
        └── work.js (code for work section)
```

`components` folder contains 21 folders with different sections and files.


## routes
In `routers` folder we used routs js. where we linked all the route for our all theme. For routing we used react-router-dom.

Routes: `routers/routs.js`

```js
import React from "react";
import { BrowserRouter as Router, Route, Switch } from "react-router-dom";

// importing all the themes
import ThemeOne from "../themes/theme-one";
import ThemeTwo from "../themes/theme-two";
import ThemeThree from '../themes/theme-three';
import ThemeFour from "../themes/theme-four";
import ThemeFive from "../themes/theme-five";
import ThemeSix from "../themes/theme-six";
import BlogTwoColumn from "../components/Blogs/BlogTwoColumn";
import BlogThreeColumn from "../components/Blogs/BlogThreeColumn";
import BlogLeftSidebar from "../components/Blogs/BlogLeftSidebar";
import BlogRightSidebar from "../components/Blogs/BlogRightSidebar";
import BlogDetailsLeftSidebar from "../components/Blogs/BlogDetailsLeftSidebar";
import BlogDetailsRightSidebar from "../components/Blogs/BlogDetailsRightSidebar";
import Reviews from "../components/ReviewSection/Reviews";
import Pricing from "../components/PricingSection/Pricing";
import DownloadPage from "../components/DownloadSection/DownloadPage";
import SubscribePage from "../components/SubscribeSection/SubscribePage";
import ThankYou from "../components/InnerSection/ThankYou";
import ComingSoon from "../components/InnerSection/ComingSoon";
import Login from "../components/Accounts/Login";
import Signup from "../components/Accounts/Signup";
import Forgot from "../components/Accounts/Forgot";
import Faq from "../components/FaqSection/Faq";
import ErrorPage from "../components/ErrorPage/404";
import ContactPage from "../components/ContactSection/ContactPage";

class MyRouts extends React.Component {
  render() {
    return (
      <div>
        <Router>
          <Switch>
            <Route exact path="/" component={ThemeOne} />
            <Route exact path="/theme-two" component={ThemeTwo} />
            <Route exact path="/theme-three" component={ThemeThree} />
            <Route exact path="/theme-four" component={ThemeFour} />
            <Route exact path="/theme-five" component={ThemeFive} />
            <Route exact path="/theme-six" component={ThemeSix} />
            <Route exact path="/BlogTwoColumn" component={BlogTwoColumn} />
            <Route exact path="/BlogThreeColumn" component={BlogThreeColumn} />
            <Route exact path="/BlogLeftSidebar" component={BlogLeftSidebar} />
            <Route exact path="/BlogRightSidebar" component={BlogRightSidebar} />
            <Route exact path="/BlogDetailsLeftSidebar" component={BlogDetailsLeftSidebar} />
            <Route exact path="/BlogDetailsRightSidebar" component={BlogDetailsRightSidebar} />
            <Route exact path="/Reviews" component={Reviews} />
            <Route exact path="/Pricing" component={Pricing} />
            <Route exact path="/DownloadPage" component={DownloadPage} />
            <Route exact path="/SubscribePage" component={SubscribePage} />
            <Route exact path="/ThankYou" component={ThankYou} />
            <Route exact path="/ComingSoon" component={ComingSoon} />
            <Route exact path="/Login" component={Login} />
            <Route exact path="/Signup" component={Signup} />
            <Route exact path="/Forgot" component={Forgot} />
            <Route exact path="/Faq" component={Faq} />
            <Route exact path="/ErrorPage" component={ErrorPage} />
            <Route exact path="/ContactPage" component={ContactPage} />
          </Switch>
        </Router>
      </div>
    );
  }
}
export default MyRouts;

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
