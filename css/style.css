// ------------------------------
// REGISTER
// ------------------------------

const registerForm = document.getElementById("registerForm");

if (registerForm) {

    registerForm.addEventListener("submit", function(event) {

        event.preventDefault();

        const name = document.getElementById("registerName").value;
        const email = document.getElementById("registerEmail").value;
        const password = document.getElementById("registerPassword").value;
        const confirmPassword = document.getElementById("confirmPassword").value;

        if (password !== confirmPassword) {

            alert("Passwords do not match!");
            return;

        }

        const user = {
            name: name,
            email: email,
            password: password
        };

        localStorage.setItem("user", JSON.stringify(user));

        alert("Registration successful!");

        window.location.href = "login.html";

    });

}


// ------------------------------
// LOGIN
// ------------------------------

const loginForm = document.getElementById("loginForm");

if (loginForm) {

    loginForm.addEventListener("submit", function(event) {

        event.preventDefault();

        const email = document.getElementById("loginEmail").value;
        const password = document.getElementById("loginPassword").value;

        const savedUser = JSON.parse(localStorage.getItem("user"));

        if (!savedUser) {

            alert("Please register first.");
            return;

        }

        if (
            email === savedUser.email &&
            password === savedUser.password
        ) {

            localStorage.setItem("loggedIn", "true");

            alert("Login successful!");

            window.location.href = "dashboard.html";

        } else {

            alert("Invalid email or password.");

        }

    });

}


// ------------------------------
// LOGOUT
// ------------------------------

const logoutButton = document.getElementById("logout");

if (logoutButton) {

    logoutButton.addEventListener("click", function(event) {

        event.preventDefault();

        localStorage.removeItem("loggedIn");

        window.location.href = "index.html";

    });

}


// ------------------------------
// CREATE BLOG
// ------------------------------

const blogForm = document.getElementById("blogForm");

if (blogForm) {

    blogForm.addEventListener("submit", function(event) {

        event.preventDefault();

        const title = document.getElementById("blogTitle").value;
        const category = document.getElementById("blogCategory").value;
        const content = document.getElementById("blogContent").value;

        const blog = {

            title: title,
            category: category,
            content: content,
            date: new Date().toLocaleDateString()

        };

        let blogs =
            JSON.parse(localStorage.getItem("blogs")) || [];

        blogs.push(blog);

        localStorage.setItem(
            "blogs",
            JSON.stringify(blogs)
        );

        alert("Blog published successfully!");

        window.location.href = "dashboard.html";

    });

}


// ------------------------------
// DISPLAY BLOGS
// ------------------------------

const myBlogs = document.getElementById("myBlogs");

if (myBlogs) {

    const blogs =
        JSON.parse(localStorage.getItem("blogs")) || [];

    myBlogs.innerHTML = "";

    if (blogs.length === 0) {

        myBlogs.innerHTML =
            "<p>No blogs created yet.</p>";

    } else {

        blogs.forEach(function(blog, index) {

            const blogCard = document.createElement("article");

            blogCard.className = "dashboard-card";

            blogCard.innerHTML = `

                <div>

                    <h3>${blog.title}</h3>

                    <p>
                        <strong>Category:</strong>
                        ${blog.category}
                    </p>

                    <p>
                        ${blog.content}
                    </p>

                    <small>
                        Published on ${blog.date}
                    </small>

                </div>

                <div>

                    <button
                        class="delete-btn"
                        onclick="deleteBlog(${index})">
                        Delete
                    </button>

                </div>

            `;

            myBlogs.appendChild(blogCard);

        });

    }

}


// ------------------------------
// DELETE BLOG
// ------------------------------

function deleteBlog(index) {

    const confirmDelete =
        confirm("Are you sure you want to delete this blog?");

    if (!confirmDelete) {
        return;
    }

    let blogs =
        JSON.parse(localStorage.getItem("blogs")) || [];

    blogs.splice(index, 1);

    localStorage.setItem(
        "blogs",
        JSON.stringify(blogs)
    );

    location.reload();

}
