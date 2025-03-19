<script>
    let activeTab = "general";
</script>

<main>
    <h1>Who am I?</h1>
    <div data-aos="fade-up" data-aos-duration="1300">
        <div class="container">
            <div class="imgarea">
                <img src="aboutme.png" alt="profile in the about page" class="about-profile">
                <svg class="blob-shape" xmlns="http://www.w3.org/2000/svg" width="599" height="540" viewBox="0 0 599 540" fill="none">
                    <path 
                        d="M589 246.5C547.464 432 468.788 540 320.5 540C172.212 540 0 377.275 0 208C0 38.7247 172.212 0 320.5 0C468.788 0 640.5 16.5 589 246.5Z" 
                        fill={activeTab === "general" ? "#EEDBD4" : activeTab === "qualification" ? "#BBB2AF" : "#E5C3C2"}
                    />
                </svg>
            </div>
            <div class="textarea">
                <div class="tablist">
                    <button 
                        type="button" 
                        role="tab" 
                        aria-selected={activeTab === "general"} 
                        on:click={() => activeTab = "general"} 
                        class:active={activeTab === "general"}
                        style="background-color: {activeTab === 'general' ? '#EEDBD4' : 'transparent'}; color: {activeTab === 'general' ? 'white' : '#463F3C'};">
                        General
                    </button>
                    <button 
                        type="button" 
                        role="tab" 
                        aria-selected={activeTab === "qualification"} 
                        on:click={() => activeTab = "qualification"} 
                        class:active={activeTab === "qualification"}
                        style="background-color: {activeTab === 'qualification' ? '#BBB2AF' : 'transparent'}; color: {activeTab === 'qualification' ? 'white' : '#463F3C'};">
                        Qualification
                    </button>
                    <button 
                        type="button" 
                        role="tab" 
                        aria-selected={activeTab === "skills"} 
                        on:click={() => activeTab = "skills"} 
                        class:active={activeTab === "skills"}
                        style="background-color: {activeTab === 'skills' ? '#E5C3C2' : 'transparent'}; color: {activeTab === 'skills' ? 'white' : '#463F3C'};">
                        Skills
                    </button>
                </div>
            
                <div class="textlist">
                    {#if activeTab === "general"}
                        <div data-state="active" class="active-general">
                            <h2>A self-driven learner with a passion for growth</h2>
                            <p>With a background in Nursing Science, I transitioned into tech after moving to the Netherlands for my relationship. I specialize in UX/UI design and front-end development, and I’m passionate about creating intuitive, user-centered digital experiences.</p>
                        </div>
                    {:else if activeTab === "qualification"}
                        <div data-state="active" class="active-qualification">
                            <h2>My journey is always accompanied by challenges</h2>
                            <div class="qualification-list">
                                <div class="education">
                                    <div class="title">
                                        <img src="education-icon.png" alt="education" class="qualification-icon">
                                        <h3>Education</h3>
                                    </div>
                                    <div class="education-list">
                                        <div class="hbo">
                                            <h4>De Haagse Hogeschool</h4>
                                            <h5>HBO Prophedeuse Bachelor of User Experience Design</h5>
                                            <p>2023 / 2024</p>
                                        </div>
                                        <div class="bachelor">
                                            <h4>Dong-Eui University</h4>
                                            <h5>Bachelor of Nursing Science</h5>
                                            <p>2019 / 2023</p>
                                        </div>
                                    </div>
                                </div>
                                <div class="experience">
                                    <div class="title">
                                        <img src="work-icon.png" alt="work" class="qualification-icon">
                                        <h3>Experience</h3>
                                    </div>
                                    <div class="experience-list">
                                        <div class="developer">
                                            <h4>Front-end Developer</h4>
                                            <h5>Self-employed</h5>
                                            <p>2024 / Present</p>
                                        </div>
                                        <div class="media">
                                            <h4>Media Support Staff</h4>
                                            <h5>Korean Culture and Information Service</h5>
                                            <p>2023</p>
                                        </div>
                                        <div class="bachelor">
                                            <h4>Psychiatric Nursing Internship </h4>
                                            <h5>Diverse medical settings</h5>
                                            <p>2020 / 2022</p>
                                        </div>
                                    </div>
                                </div>
                                <div class="experience"></div>
                            </div>
                        </div>
                    {:else if activeTab === "skills"}
                        <div data-state="active" class="active-skills">
                            <h2>Skills I provide to create real-life impact</h2>
                            <div class="skill-list">
                                <img width="48" height="48" src="https://img.icons8.com/color/48/html-5--v1.png" alt="html-5--v1"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/css3.png" alt="css3"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/javascript--v1.png" alt="javascript--v1"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/typescript.png" alt="typescript"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/figma--v1.png" alt="figma--v1"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/adobe-photoshop--v1.png" alt="adobe-photoshop--v1"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/visual-studio--v2.png" alt="visual-studio--v2"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/git.png" alt="git"/>
                                <img width="48" height="48" src="https://img.icons8.com/ios-filled/50/github.png" alt="github"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/docker.png" alt="docker"/>
                                <img width="48" height="48" src="https://img.icons8.com/color/48/react-native.png" alt="react-native"/>
                                <img width="48" height="48" src="svelte-icon.png" alt="svelte"/>
                            </div>
                        </div>
                    {/if}
                </div>
            </div>
        </div>
    </div>
</main>

<style>
/* ============================== */
/* ============================== */
/*   Universal Container Setting  */
/* ============================== */
/* ============================== */
.container {
    max-width: 90vw;
    min-height: 65vh;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

/* ======================== */
/* ======================== */
/*     Image Section        */
/* ======================== */
/* ======================== */
.imgarea {
    position: relative;     /* Image Placement */
    width: 36vw;
    height: 36vw;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-right: 4rem; /* MARGIN between .imagearea (left) and .textarea (right) */
}

    /* Image file */
    .about-profile {
        position: absolute;
        width: 30vw;
        border-radius: 50%;
        top: 50%;
        left: 52%;
        transform: translate(-50%, -50%);
        z-index: 2;
    }

    /* Blob Shape */
    .blob-shape {
        position: absolute;
        max-width: 36vw;
        top: 45%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 1;
    }

/* ======================== */
/* ======================== */
/*     Text Section         */
/* ======================== */
/* ======================== */
.textarea {
    margin: 0 auto; /* !Ensure the fixed width of nav bar*/
    max-width: 618px; /* !Ensure the fixed width of nav bar*/
}

    /* ======================== */
    /*  Active State - General  */
    /* ======================== */
    .tablist {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        border: 1px solid #463F3C;
        border-radius: 50px;
        padding: 0.25rem 0.5rem;
        width: 100%;
        max-width: 600px; /* Ensure the tab list has a fixed width */
        margin: 2rem auto;
        text-align: center;
        }

    .tablist > button {
        border: none;
        background-color: transparent;
        padding: 1rem; /* Consistent padding for each button */
        transition: background-color 0.3s ease, color 0.3s ease;
        flex-grow: 1; /* Ensure buttons grow equally */
        cursor: pointer;
        text-align: center;
    }

    /* Ensure all buttons are equally sized */
    .tablist button {
        width: 100%; /* Make sure each button fills its container */
        min-width: 200px; /* Ensure minimum size of each button!! */
    }

    /* Tab button active state */
    .tablist button.active {
        background-color: #EEDBD4; /* Active tab background color */
        color: white; /* Active tab text color */
        border-radius: 50px;
    }

    /* Hover state */
    .tablist button:hover {
        background-color: #F0E0C9; /* Hover background color */
        color: white;
    }

    .active-general, .active-qualification, .active-skills {
        max-width: 700px;
        margin: 3rem 0;
    }

    /* ======================== */
    /*  Qualification Section   */
    /* ======================== */
    .active-qualification h2 {
        margin: 0;
    }

    .education-list, .experience-list {
        margin-left: 1.5rem;
        padding-left: 2.5rem;
        border-left: 2px solid #BBB2AF;
    }

    .qualification-icon {
        margin-right: 1rem;
    }


    .title {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .qualification-list {
        display: grid;
        grid-template-columns: repeat(2, 1fr); /* Two equal columns */
    }

    .education, .experience {
        display: flex;
        flex-direction: column;
        padding: 1rem;
    }

    /* ======================== */
    /*      Skill Section       */
    /* ======================== */
    .skill-list {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(60px, 1fr)); /* Creates a responsive grid */
        gap: 20px; /* Adds space between each icon */

        justify-items: center; /* Centers each icon in its grid cell */
        max-width: 530px;
        margin: 4rem auto;
    }

    .skill-list img {
        object-fit: contain;
        transition: transform 0.3s ease-in-out;
    }

    /* Optional hover effect for icons */
    .skill-list img:hover {
        transform: scale(1.2); /* Enlarges the icon on hover */
    }


/* ======================== */
/*      Font Setting        */
/* ======================== */
    h1 {
        font-size: 2.5rem;
        margin-top: 0;
        text-align: center;
    }

    h2 {
        font-weight: 700;
        font-size: 1.5rem;
        text-align: center;
    }

    .active-general p {
        margin-left: 1.5rem;
    }

    button {
        font-size: 1.1rem;

    }

    p {
        font-size: 1.1rem;
        line-height: 2;
    }

    h3 {
        font-size: 1.5rem;
        font-weight: 600;
    }

    h4 {
        font-size: 1.2rem;
        font-weight: 500;
        margin: 0.5rem 0;
    }

    h5 {
        font-size: 0.9rem;
        font-weight: 400;
        margin: 0;
    }

    .qualification-list p {
        font-size: .8rem;
        font-weight: 100;
        margin: 0;
    }

/* ======================== */
/* ======================== */
/*       Media Query        */
/* ======================== */
/* ======================== */
    @media (min-width: 1740px) {
        h1 {
            margin-top: 5rem;
        }   

        .container {
            max-width: 70%;
            margin-top: 5rem;
        }
        .imgarea {
            max-width: 600px;
            max-height: 600px;
            
        }
        /* Ensure the image size stays smaller than or equal to the blob size */
        .about-profile {
            max-width: 448px; /* Adjust this to be slightly smaller than the blob */
            top: 48%;
        }

        .blob-shape {
            max-width: 538px;
            width: 36vw; /* Ensuring the blob stays the same */
        }

    }
    
    @media (min-width: 1225px ) and (max-width: 1739px){
        .container {
            margin-top: 6rem;
        }
    }

    @media (min-width: 995px ) and (max-width: 1224px){

        .container {
            min-width: 100vw;
            margin-top: 4rem;
        }

        .imgarea {
            margin-left: 4rem;
        }

        .textarea {
            margin-right: 2rem;
        }
    }

    @media (max-width: 994px) {

        .imgarea {
            display: none;
        }
    }

    @media (max-width: 684px) {
        .imgarea {
            display: none;
        }

        .textarea {
            width: 80vw;
        }

        .tablist {
            border: none;
            flex-direction: column;
            margin: 0;
        }

        .tablist > button {
            padding: .5rem;
            max-width: 240px;
            margin: 0 auto;
        }

        .qualification-list {
        display: flex;
        flex-direction: column;
    }

/* Font */
        h2 {
            font-size: 1.25rem;
        }

        h3, h4 {
            font-size: 1.2rem;
            margin: .25rem 0;
        }
    }

</style>
