<script>
    import { page } from '$app/stores';
    import { get } from 'svelte/store';
</script>

<main>
    <h1>My Projects</h1>
        <div class="container">
            <div class="work-list">
                <div data-aos="fade-up" data-aos-duration="1500">
                    <div class="work-1 work-container">
                        <img src="https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/static/prototype1.png" alt="portfolio prototype">
                        <div class="textarea">
                            <h2>Portfoilo Website</h2>
                            <p>The website you’re on right now.<br/>Built with Sveltekit. Deployed on Cloudflare.</p>
                        </div>
                    </div>
                </div>
                <div data-aos="fade-up" data-aos-duration="1500">
                    <div class="work-2 work-container">
                        <img src="https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/static/prototype2.png" alt="wedding prototype">
                        <div class="textarea">
                            <h2>Wedding Invitation Website</h2>
                            <p>A website for inviting people to wedding ceremony.<br/>Built with Sveltekit. Deployed on Cloudflare.</p>
                            <a href="https://yejeongandhakrim.pages.dev" class="contact-btn button"><span>Go to website</span></a>
                        </div>
                    </div>
                </div>
                <div data-aos="fade-up" data-aos-duration="1500">
                    <div class="work-3 work-container">
                        <img src="https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/static/prototype3.png" alt="esse prototype">
                        <div class="textarea">
                            <h2>essebv.com</h2>
                            <p>My very first project built with HTML, CSS, and Javascript.</p>
                            <a href="https://www.essebv.com" class="contact-btn button"><span>Go to website</span></a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</main>

<style>
.container {
    max-width: 90vw;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-wrap: wrap; /* Allow wrapping in smaller screens */
}

.work-container {
    display: flex;
    flex-direction: row; /* Align the image and text side by side */
    align-items: center; /* Vertically align the image and text */
    justify-content: space-between; /* Space out image and text */
    margin-bottom: 2rem; /* Add space between each work container */
    width: 100%; /* Full width of each work container */
    flex-basis: 30%; /* Ensure the content doesn't get too narrow on smaller screens */
}

.textarea {
    width: 50%;
    padding: 1rem;
    text-align: left; /* Align text to the left */
    display: flex;
    flex-direction: column;
    justify-content: center; /* Vertically center the text */
}

img {
    max-width: 60%; /* Limit the image width */
    margin-right: 1.5rem; /* Space between the image and text */
}

.button {
    border-radius: 50px;
    text-align: center;
    text-decoration: none;
    font-size: 1rem;
    padding: 1rem 2rem;
    width: 130px;
    display: inline-block;
    overflow: hidden;
    box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.1);
}

.button span {
    position: relative;
    transition: 0.5s ease;
}

.button span:after {
    content: '\00bb'; /* >> */
    position: absolute;
    opacity: 0;
    top: 0;
    right: -20px;
    transition: 0.5s ease;
}

.button:hover {
    box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.2);
}

.button:hover span {
    padding-right: 20px;
}

.button:hover span:after {
    opacity: 1;
    right: 0;
}

.contact-btn {
    background: #EBE2DE;
    color: #463F3C;
}

/* Font Setting */
h1 {
    font-size: 2.5rem;
    margin-top: 4rem;
    text-align: center;
}

h2 {
    font-size: 2rem;
    font-weight: 600;
}

p {
    font-weight: 200;
    line-height: 1.5;
    margin-bottom: 2rem;
}

/* ======================== */
/*       Media Query        */
/* ======================== */
@media (min-width: 1174px) {
    .work-list {
        margin: 0 auto;
    }
    img {
        max-width: 800px; /* Scale the image width */
    }

    h2, p, a {
        margin: 1rem 0;
    }

    h2 {
        font-size: 2.5rem;
    }

    p {
        font-size: 1.3rem;
    }
}
@media (max-width: 768px) {
    .container {
        flex-direction: column; /* Stack content vertically on smaller screens */
        align-items: center;
        width: 80vw;
        justify-content: center; /* Center content vertically */        
    }

    .work-container {
        flex-direction: column; /* Stack image and text vertically on small screens */
    }

    .textarea {
        width: 80%; /* Reduce the width of the text area on smaller screens */
        text-align: center; /* Center-align the text on smaller screens */
        display: flex; /* Add flexbox to center the content */
        flex-direction: column;
        justify-content: center; /* Center the button and text vertically */
        align-items: center; /* Center the content horizontally */
    }

    img {
        max-width: 80%; /* Scale the image width */
        margin: 0;
    }

    h2, p {
        margin: 1rem 0;
    }

    h2 {
        font-size: 1.5rem;
    }

    p {
        font-size: 1.1rem;
    }



    /* Button */
    .button {
        display: inline-block;
        padding: 1rem 2rem;
        text-align: center;
        margin-top: 1rem;
    }
}

</style>