Overview
The Ramen Rating App is a fun and interactive project for viewing, rating, and adding ramen dishes to a dynamic menu. It showcases core JavaScript concepts like DOM manipulation, event handling, and form integration.

Features
Interactive Menu: Browse a collection of ramen dishes with images.

Detailed View: Click on a ramen image to see its details.

Add New Ramen: Submit a form to add your favorite ramen dish to the menu.

Custom Styling: A polished and visually appealing user interface.

File Structure
Ramen-Rating-App/
│── index.html       # Main HTML layout
│── css/
│   └── style.css    # App styling
│── images/          # Folder for ramen images
│── index.js         # JavaScript logic
│── README.md        # Project documentation
Technologies Used
HTML: Building the webpage structure.

CSS: Creating the layout and styling.

JavaScript: Enabling interactivity and event handling.

How to Use
Clone the repository:

bash
git clone https://github.com/your-username/ramen-rating-app.git
Navigate into the project directory:

bash
cd ramen-rating-app
Open the app in your browser:

bash
open index.html
Key Functionalities
displayRamens()
Automatically loads ramen images into the menu when the page is loaded.

javascript
function displayRamens() {
    ramens.forEach(ramen => {
        const img = document.createElement("img");
        img.src = ramen.image;
        img.alt = ramen.name;
        img.classList.add("ramen-thumbnail");
        img.addEventListener("click", () => handleClick(ramen));
        ramenMenu.appendChild(img);
    });
}
handleClick()
Displays detailed information about the selected ramen dish.

javascript
function handleClick(ramen) {
    detailImage.src = ramen.image;
    detailName.textContent = ramen.name;
    detailRestaurant.textContent = `Restaurant: ${ramen.restaurant}`;
    detailRating.textContent = `Rating: ${ramen.rating}`;
    detailComment.textContent = `Comment: ${ramen.comment}`;
}
addSubmitListener()
Handles form submission to add a new ramen dish to the menu.

javascript
function addSubmitListener() {
    newRamenForm.addEventListener("submit", (e) => {
        e.preventDefault();
        
        const newRamen = {
            id: ramens.length + 1,
            name: document.getElementById("name").value,
            restaurant: document.getElementById("restaurant").value,
            image: document.getElementById("image").value,
            rating: document.getElementById("rating").value,
            comment: document.getElementById("comment").value
        };
        
        ramens.push(newRamen);
        
        const img = document.createElement("img");
        img.src = newRamen.image;
        img.alt = newRamen.name;
        img.classList.add("ramen-thumbnail");
        img.addEventListener("click", () => handleClick(newRamen));
        ramenMenu.appendChild(img);

        newRamenForm.reset();
    });
}
Contribution
Contributions are welcome! Feel free to fork this repository, make improvements, and submit pull requests.

License
This project is licensed under the MIT License.

Author 
this project was created and designed by lenny Ndiu Kimanthi
