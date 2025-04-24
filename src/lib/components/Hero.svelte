<script lang="ts">
    import { page } from '$app/stores';
    import { onMount } from "svelte";

    // @ts-ignore
    import AOS from 'aos';

    onMount(() => {
        AOS.init();
    });
</script>

<main>
    <div class="spacer layer1 container">
        <div class="textarea left">
            <div data-aos="fade-up"
            data-aos-anchor-placement="top-bottom" data-aos-duration="1300">
                <p>Junior Web Developer</p>
                <h1>Hello, I'm Hyewon</h1>
                <h2>I am a Junior Web Developer based in the Netherlands. My passion lies in experimenting with technology and exploring 3D web development.</h2>
                <div class="buttons">
                    <a href="/contact" class:active={$page.url.pathname === '/contact'} class="contact-btn button"><span>Contact </span></a>
                    <a href="https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/CV%20-%20Hyewon%20Im.pdf" class="cv-btn button"><span>Download CV </span></a>
                </div>
            </div>
        </div>
        <div class="imgarea right">
            <div data-aos="fade-left" data-aos-duration="1300">
                <img src="https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/static/laptop-nobg.png" alt="main in the hero page" class="main-profile">
                <svg class="svg-shape first" xmlns="http://www.w3.org/2000/svg" width="388" height="573" viewBox="0 0 388 573" fill="none">
                <path d="M387.586 255.689C387.586 396.902 408.113 709.1 159.985 506.614C193.793 277.923 0 396.902 0 255.689C0 114.476 86.7642 0 193.793 0C300.822 0 387.586 114.476 387.586 255.689Z" fill="#ADA29E"/>
              </svg>
              <svg class="svg-shape second" xmlns="http://www.w3.org/2000/svg" width="386" height="620" viewBox="0 0 386 620" fill="none">
                <path d="M376.401 310.301C343.705 456.319 291.17 783.564 99.3069 520.728C184.787 291.539 -29.227 372.814 3.46893 226.795C36.1649 80.7768 146.154 -18.9013 249.136 4.15811C352.118 27.2175 409.097 164.282 376.401 310.301Z" fill="#EBE2DE"/>
              </svg>
            </div>
        </div>
    </div>
</main>

<style>
    main {
        width: 100vw;
        height: 70vh;
        background: url('https://pub-6e499fd5de234ef3aba9fca203ce8d62.r2.dev/static/bg.svg') no-repeat top / cover;
        background-repeat: no-repeat;
        padding: 2rem 0;
        overflow-y: hidden;
        margin-bottom: 0;
    }

    /* Universal Container Setting */
    .container {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        max-width: 90vw;
        margin: 0 auto;
    }

    .left {
        display: flex;
        flex-direction: column;
        max-width: 40vw;
    }

    .buttons {
        margin: 3rem 0;
        cursor: pointer;
        display: flex;
        flex-direction: row;
        gap: 20px;
    }

    .button {
        border-radius: 50px;
        text-align: center;
        text-decoration: none;
        font-size: 1rem;
        padding: 1rem 2rem;
        width: 130px;
        display: inline-block; /* Not to change the size of the button padding */
        overflow: hidden; /* Not to change the size of the button padding */
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

    .cv-btn {
        background: #EBE2DE;
        color: #463F3C;
    }

    .right {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .main-profile {
        width: 250px;
        top: -50px;
        position: relative; /* SVG 위에 배치 */
        z-index: 3; /* 이미지가 가장 위로 오도록 설정 */
    }

    .svg-shape {
        position: absolute; /* 이미지를 기준으로 절대 배치 */
        width: 100%; /* 부모 크기에 맞게 조정 */
        height: auto;
    }

    .svg-shape.first {
        z-index: 2;
        left: 10px;
        top: 20px;
    }

    .svg-shape.second {
        z-index: 1;
        left: 60px;
        top: 20px;
    }

    .textarea {
        margin: 0;
        margin-top: 4.5rem;
        max-width: 550px;
    }

    /* Font */
    h1 {
            margin: 1rem 0 2rem 0;
            font-weight: 800;
            font-size: 3rem;
            letter-spacing: 1px;

    }

    h2 {
            margin: 0;
            font-size: 1.1rem;
            font-weight: 300;
            max-width: 460px;
    }

    p {
        margin: 0;
        letter-spacing: .6em;
        text-align: center;
    }

    /* ======================== */
    /* ======================== */
    /*       Media Query        */
    /* ======================== */
    /* ======================== */
    @media (min-width: 1498px) {
        main {
            height: 100vh;
        }
        .container {
            margin-top: 7rem;
            max-width: 80vw;
        }

        .textarea {
            max-width: 100vw;
            margin-top: 0;
        }
        
        .main-profile {
            width: 300px;
            top: -100px;
        }
        
        h1 {
            font-size: 5rem;
        }

        h2 {
            font-size: 1.4rem;
            line-height: 2;
            max-width: 700px;
        }

        p {
            margin-top: 0;
            font-size: 1.1rem;
            letter-spacing: .2em;
            text-align: left;
        }
    }

    @media (min-width: 1335px) and (max-width: 1497px) {
        main {
            height: 100vh;
        }

        .container {
            margin-top: 4rem;
        }
    }


    @media (max-width: 684px) {
        main {
            min-height: 90vh;
        }

        .textarea {
            max-width: 80vw;
            text-align: center;
            margin: 0 auto;
            gap: 30px;
        }

        .right {
            display: none;
        }

        .buttons {
            flex-direction: column;
            margin: 0 auto;
            margin-top: 4rem;
            gap: 2rem;
        }

        .button {
            font-size: 1rem;
            padding: 1rem 1.5rem;
            width: 150px;
            margin: 0 auto;
        }

        /* Font */
        h1 {
            font-size: 3.5rem;
        }

        h2 {
            font-size: 1.1rem;
            line-height: 2;
        }

        p {
            margin-top: .5rem;
            font-size: .7rem;
            letter-spacing: .2em;
        }
    }
</style>
