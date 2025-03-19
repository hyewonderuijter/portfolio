<script>
    import { page } from '$app/stores';
    import { get } from 'svelte/store';
</script>

<main>
    
    <div class="container">
        <div class="textarea">
            <h1>Let's connect!</h1>
            <p>Ready to bring innovative ideas to life.</p>
        </div>
        <div class="contact-list">
            <a href="/contact" class:active={get(page).url.pathname === '/contact'} class="contact-btn button"><span>Contact</span></a>
            <div class="social-icons">
                <a href="https://www.linkedin.com/in/hyewonim"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/linkedin.png" alt="linkedin" class="social-icon-img icon"/></a>
                <a href="https://github.com/hyewonderuijter"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/github.png" alt="github" class="social-icon-img icon"/></a>
                <a href="https://www.instagram.com/uomahy__/"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/instagram-new.png" alt="instagram-new" class="social-icon-img icon"/></a>
            </div>
        </div>
    </div>
</main>

<style>

main {
    background: url('https://www.hyewonim.com/static/footer-bg.svg') no-repeat bottom / cover;
    height: 40vh;
    display: flex;
    align-items: flex-end; /* Align children at the bottom */
}

.container {
    display: flex;
    flex-direction: row; /* Ensure items are stacked vertically */
    justify-content: space-between; /* Align items to the bottom */
    align-items: center; /* Center the items horizontally */
    width: 100%;
    margin: 0 6rem;
}

.textarea {
    display: flex;
    flex-direction: column;
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
    background: #ADA29E;
    color: #fff;
}

/* Font Setting */
h1 {
    font-size: 3rem;
    max-width: 70vw;
    margin: 0;
    text-align: left;
    color: #484848;
}

p {
    font-size: 1.2rem;
    font-weight: 200;
}

h1, p {
    margin-right: 2rem;
}

.social-icons {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        max-width: 20%;
        margin: 0 auto;
        margin-top: 1rem;
    }

/* ======================== */
/*       Media Query        */
/* ======================== */
@media (min-width: 1170px) {
    main {
        align-items: center;
    }

    .container {
        max-width: 65vw;
        margin: 0 auto;
    }

    h1 {
        font-size: 4.5rem;
    }

    p {
        margin: 0;
        font-size: 2rem;
    }

    .social-icons {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        max-width: 20%;
        margin: 0 auto;
        margin-top: 1rem;
        gap: 2rem;
    }

    .contact-list {
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        width: 50%;
    }
}

@media (min-width: 1170px) and ((max-width: 1470px)) {
    .social-icons {
        display: none;
    }
}

@media (max-width: 686px) {
    main {
        align-items: flex-end; /* Align children at the bottom */
    }
    .container {
            width: 80vw;
            margin: 0 auto;
    }

    h1 {
        font-size: 1.5rem;
    }

    p {
        font-size: .8rem;
    }

    /* Button */
    .button {
        padding: .75rem .6rem;
        font-size: .8rem;
    }

    .social-icons {
        display: none;
    }
    
    }

</style>