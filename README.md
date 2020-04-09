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
Template `index.js` structure looks like this-
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
Template `app.js` structure looks like this-
```js
import React from 'react';

// importing MyRouts where we located all of our theme
import MyRouts from './routers/routes'

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


## routes
In `routers` folder we used `routes.js`. Where we linked all the route for our all theme. For routing we used react-router-dom.

Routes: `routers/routes.js`

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
            <Route path="/theme-two" component={ThemeTwo} />
            <Route path="/theme-three" component={ThemeThree} />
            <Route path="/theme-four" component={ThemeFour} />
            <Route path="/theme-five" component={ThemeFive} />
            <Route path="/theme-six" component={ThemeSix} />
            <Route path="/blog-two-column" component={BlogTwoColumn} />
            <Route path="/blog-three-column" component={BlogThreeColumn} />
            <Route path="/blog-left-sidebar" component={BlogLeftSidebar} />
            <Route path="/blog-right-sidebar" component={BlogRightSidebar} />
            <Route path="/blog-details-left-sidebar" component={BlogDetailsLeftSidebar} />
            <Route path="/blog-details-right-sidebar" component={BlogDetailsRightSidebar} />
            <Route path="/reviews" component={Reviews} />
            <Route path="/pricing" component={Pricing} />
            <Route path="/download-page" component={DownloadPage} />
            <Route path="/subscribe-page" component={SubscribePage} />
            <Route path="/thank-you" component={ThankYou} />
            <Route path="/coming-soon" component={ComingSoon} />
            <Route path="/login" component={Login} />
            <Route path="/signup" component={Signup} />
            <Route path="/forgot" component={Forgot} />
            <Route path="/faq" component={Faq} />
            <Route path="/error-page" component={ErrorPage} />
            <Route path="/contact-page" component={ContactPage} />
          </Switch>
        </Router>
      </div>
    );
  }
}
export default MyRouts;

```


## components
Under `components` folder we wrote all of our components individually. 
We have written these components to make the developer’s life easy. 
By using these basic components, For example in our components directory there is `HeaderSection`, `HeroSection` , `FooterSection` folder where we wrote our different styled component. For example `HeroSection` component-

### Component folder structure
```text
|-- components
    ....
    |-- HeroSection ( hero component folder )
        - HeroOne.js ( main demo hero section )
        - HeroTwo.js ( demo two hero section )
        ...... ( and other )
        
    |-- ContactSection ( contact folder )
        - Contact.js 
        - ContactForm.js
        - ContactPage.js
    .
    ..
    ...    
```

### Contact Section component
`ContactSection/Contact.js`
```js
import React, { Component } from 'react';
import ContactForm from './ContactForm';
import axios from 'axios';

const BASE_URL = "https://my-json-server.typicode.com/themeland/json-server-1/themeOneContactSection";

class ContactSection extends Component {
    state = {
        data: {},
        iconList: []
    }
    componentDidMount(){
        axios.get(`${BASE_URL}`)
            .then(res => {
                this.setState({
                    data: res.data,
                    iconList: res.data.iconList
                })
                // console.log(this.state.data)
            })
        .catch(err => console.log(err))
    }
    render() {
        return (
            <section id="contact" className="contact-area bg-gray ptb_100">
                <div className="container">
                    <div className="row justify-content-center">
                    <div className="col-12 col-md-10 col-lg-6">
                        {/* Section Heading */}
                        <div className="section-heading text-center">
                        <h2 className="text-capitalize">{this.state.data.heading}</h2>
                        <p className="d-none d-sm-block mt-4">{this.state.data.headingText}</p>
                        <p className="d-block d-sm-none mt-4">{this.state.data.headingTexttwo}</p>
                        </div>
                    </div>
                    </div>
                    <div className="row justify-content-between">
                    <div className="col-12 col-md-5">
                        {/* Contact Us */}
                        <div className="contact-us">
                        <p className="mb-3">{this.state.data.content}</p>
                            <ul>
                                {this.state.iconList.map((item, idx) => {
                                    return(
                                        <li key={`ci_${idx}`} className="py-2">
                                            <a className="media" href="/#">
                                                <div className="social-icon mr-3">
                                                    <i className={item.iconClass} />
                                                </div>
                                                <span className="media-body align-self-center">{item.text}</span>
                                            </a>
                                        </li>
                                    );
                                })}
                            </ul>
                        </div>
                    </div>
                    <div className="col-12 col-md-6 pt-4 pt-md-0">
                        <ContactForm />
                    </div>
                    </div>
                </div>
            </section>
        );
    }
}

export default ContactSection;
```

### Contact Form component
`ContactSection/ContactForm.js`
```js
import React, { Component } from "react";


class ContactForm extends Component {

  constructor(props) {
    super(props)
    this.myForm = React.createRef()
  }

  state = {
    name: '',
    email: '',
    subject: '',
    message: ''
  }

  changHandler = (event) => {
    this.setState({
      [event.target.name]: event.target.value
    })
  }
  submitHangler = (event) => {
    event.preventDefault();
    console.log(this.state)
    this.myForm.current.reset()
    this.setState({
      name: '',
      email: '',
      subject: '',
      message: ''
    })
    console.log(this.state)
  }

  render() {
    return (
      <div className="contact-box text-center">
        <form
          ref={this.myForm}
          onSubmit={this.submitHangler}
          className="contact-form"
          noValidate="novalidate"
        >
          <div className="row">
            <div className="col-12">
              <div className="form-group">
                <input
                type="text"
                className="form-control"
                name="name"
                placeholder="Name"
                required="required"
                onChange={this.changHandler}
                value={this.state.name}
                />
              </div>
              <div className="form-group">
                <input
                type="email"
                className="form-control"
                name="email"
                placeholder="Email"
                required="required"
                onChange={this.changHandler}
                value={this.state.email}
                />
              </div>
              <div className="form-group">
                <input
                type="text"
                className="form-control"
                name="subject"
                placeholder="Subject"
                required="required"
                onChange={this.changHandler}
                value={this.state.subject}
                />
              </div>
            </div>
            <div className="col-12">
                <div className="form-group">
                    <textarea
                    className="form-control"
                    name="message"
                    placeholder="Message"
                    required="required"
                    onChange={this.changHandler}
                    value={this.state.message}
                    />
                </div>
            </div>
            <div className="col-12">
                <button
                    type="submit"
                    className="btn btn-lg btn-block mt-3"><span className="text-white pr-3"><i className="fas fa-paper-plane" /></span>
                    Send Message
                </button>
            </div>
          </div>
        </form>
      </div>
    );
  }
}

export default ContactForm;
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
