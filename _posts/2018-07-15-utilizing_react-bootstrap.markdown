---
layout: post
title:      "Utilizing React-Bootstrap"
date:       2018-07-15 17:59:07 +0000
permalink:  utilizing_react-bootstrap
---


My previous post was dedicated to my final project at Flatiron which was an app that utilizes React/Redux for front end and Rails API backend. Recently, I've been trying to find ways to make it more aesthetically pleasing. My landing page needed some work because it previously was just a title and a button. I wanted to make the overall app more responsive and interactive. Thus, I decided to make use of React-Bootstrap, one of the most popular front-end frameworks, rebuilt for React.

To set up, I installed Bootstrap as a dependency

`npm install --save react-bootstrap`

Once installed, I added it to my app's index.js file.

`import 'bootstrap/dist/css/bootstrap.css'`

and added the following link to my index.html file

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
```

Those two steps are important because if the library isn't imported, the components aren't going to work. Once those steps have been completed, I started importing the components I would use from Bootstrap in each of my JS files.

```
import { Navbar, Nav, NavItem, MenuItem, NavDropdown } from 'react-bootstrap';
```

Next, after going over some documentation. I decided to add a Page Header to my emphasize each Skincare Ritual's title and change up the button styles to my like/dislike functions first. 

```
      <PageHeader>
        {ritual.name} <small> | {ritual.category}</small>
      </PageHeader>
      <h3>Likes: {ritual.likes}</h3>
      <Button
        bsStyle="primary"
        bsSize="small"
        onClick={ () => addLike(ritual) }
      >
      Like
      </Button>
      <Button
        bsStyle="danger"
        bsSize="small"
        onClick={ () => addDislike(ritual) }
      >
      Dislike
      </Button>
```

Making small changes like the one above really made a difference to the overall look and character of the site. The button style "primary" resulted in a blue button and the "danger" a red one. You can also control the size of the buttons with large, default, small or x-small. 

Next, I tackled fixing my NavBar. I only made a small change to add a dropdown choice for actions related to rituals. 
```
      <Navbar inverse collapseOnSelect>
        <Navbar.Header>
          <h2><a href="/">Skincare Rituals</a></h2>
        </Navbar.Header>
        <h3><NavDropdown eventKey={2} title="Rituals" id="basic-nav-dropdown">
          <MenuItem eventKey={2.1} href="/rituals">All Rituals</MenuItem>
          <MenuItem eventKey={2.2} href="/rituals/new">New Ritual</MenuItem>
        </NavDropdown></h3>
        <h3><NavItem eventKey={1} href="#">
          About
        </NavItem></h3>
      </Navbar>
```

For my landing page, I decided to add a carousel with three images I got from pexel.com. I had a little difficulty sizing the carousel to my liking but after making a few trial and errors, I found a sizing property that worked well for the page. 

```
      <Carousel>
      <Carousel.Item>
        <div className="slider-photo">
          <img alt="lipgloss" src={photo1} />
          <Carousel.Caption>
            <h1>Beauty</h1>
            <p>Skincare products recommended according to skin types</p>
          </Carousel.Caption>
        </div>
      </Carousel.Item>
      <Carousel.Item>
        <div className="slider-photo">
          <img alt="hand lotion" src={photo2} />
          <Carousel.Caption>
            <h1>Focus</h1>
            <p>Look through our collections of rituals to find one that best fits you</p>
          </Carousel.Caption>
        </div>
      </Carousel.Item>
      <Carousel.Item>
        <div className="slider-photo">
          <img alt="heart" src={photo3} />
          <Carousel.Caption>
            <h1>Community</h1>
            <p>Recommend your own rituals and rate others</p>
          </Carousel.Caption>
        </div>
      </Carousel.Item>
    </Carousel>
```

While I think the UI could still do with more work, I'm happy with what I've created using just Bootstrap. I am considering testing out other front-end frameworks to see how I can better my abilities. 
