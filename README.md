# Vue

In this repository, Vue to build a SPA (Single Page Application).


## Setup & Run

1. Type `npm install` to install packages.
1. Type `npm run dev` to run the development server.
1. Point your browser at `http://localhost:3000`.



### Two views - one for the user and one for the admin

  - Clicking on "Admin" shows the admin view, and clicking on "User" shows the user view. 


### 2. Admin view - form that adds images to the page.

  - This form accepts a URL, a description, and a title.
  - This form has a "submit" button.
  - After clicking the button, the image appears on the page in the user view.

### 3. User view - show images of all projects, and update featured project when clicked.

  - Three default images.
  - Event listener on each image element on your page. When the image is clicked, it replaces the featured image at the top of the page.
  - Clicking on other images removes the current featured image and appends a new one.
  - The featured image contains the image, title, and description.
  - The first project is the default featured project.

## Notes

  - This is an assignment from CodeOp school in Barcelona from a Vue workshop sequence
