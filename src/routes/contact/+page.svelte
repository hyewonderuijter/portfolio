<script lang="ts">
    import { DotLottieSvelte } from '@lottiefiles/dotlottie-svelte';
</script>

<main>
    <div class="container">
        <div class="textarea">
            <h1>Let's Work <br/><span>Together</span></h1>
            <p>I’m always open for a conversation—whether it’s about a potential project, seeking advice, asking questions, or simply networking. Feel free to contact me by clicking one of the icons below!</p>
            
            <!-- Contact Icons -->
            <div class="icon-container">
                <!-- LinkedIn Icon -->
                <a href="https://www.linkedin.com/in/hyewonim" target="_blank" class="icon linkedin">
                    <img width="50" height="50" src="https://img.icons8.com/ios-filled/50/linkedin.png" alt="linkedin"/>
                </a>
                <!-- Email Icon -->
                <a href="mailto:hyewon.im@icloud.com" class="icon email">
                    <img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/new-post.png" alt="new-post"/>
                </a>
                <!-- Phone Icon -->
                <a href="tel:+31657702836" class="icon phone">
                    <img width="50" height="50" src="https://img.icons8.com/ios-filled/50/phone-disconnected.png" alt="phone-disconnected"/>
                </a>
            </div>
        </div>
        
        <!-- DotLottie animation component -->
        <div class="blob">
            <DotLottieSvelte
                src="https://lottie.host/be944de9-aeb3-4108-8afe-9d9cdf0e036f/QfgWG8INx1.lottie"
                loop
                speed={0.5}
                autoplay
            />
        </div>
    </div>
</main>

<style>
    main {
        height: 75vh;
    }

    .container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        width: 80vw;
        margin: 0 auto;
    }

    .textarea {
        text-align: left;
    }

    .blob {
        width: auto;
        height: 500px;
    }

    h1 {
        font-size: 3rem;
        margin: 0 0 1rem 0;
    }

    p {
        font-size: 1.1rem;
        font-weight: 200;
        max-width: 400px;
        line-height: 1.7;
    }

    span {
        background-color: #BEB096;
        padding: .25rem 1rem;
        border-radius: 5px;    
        color: #000;
    }

    /* Contact Icons */
    .icon-container {
        display: flex;
        gap: 1.5rem;
    }

    img {
        width: 30px;
        height: 30px;
    }

    .icon {
        display: inline-flex;
        justify-content: center;
        align-items: center;
        width: 40px;
        height: 40px;
        background-color: #fff;
        border: 1px solid #000;
        border-radius: 50%;
        color: white;
        text-decoration: none;
        transition: background-color 0.3s ease;
    }

    .icon.linkedin:hover {
        background-color: #0077b5; /* LinkedIn blue */
    }

    .icon.email:hover {
        background-color: #ffa159; /* Email red */
    }

    .icon.phone:hover {
        background-color: #2ecc71; /* Phone green */
    }

    /* Media Query for Small Screens */
    @media (min-width: 1200px){
        .container {
            max-width: 900px;
            margin-top: 3rem;
        }

        h1 {
            font-size: 4rem;
        }

        p {
            font-size: 1.3rem;
            font-weight: 200;
            max-width: 450px;
        }
    }

    @media (max-width: 768px) {
        .container {
            align-items: center;
            flex-direction: column; /* Stack content vertically on smaller screens */
            text-align: center; /* Center-align text */
            justify-content: center; /* Vertically center the content */
            height: 70vh; /* Full viewport height */
        }
        .icon-container{
            gap: 0;
            justify-content: space-between;
        }

        .icon {
            margin: 0 auto;
        }

        img {
            width: 24px;
            height: 24px;
        }

        .icon {
            width: 40px;
            height: 40px;
        }

        .textarea {
            text-align: center;
        }

        .blob {
            display: none; /* Hide blob */
        }

        h1 {
            font-size: 2.5rem;
        }

        p {
            font-size: .8rem;
            margin-bottom: 2rem;
        }
    }

</style>
