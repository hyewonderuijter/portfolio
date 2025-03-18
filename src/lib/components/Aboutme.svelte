<script>
    let activeTab = "general";
</script>

<main>
    <h1>Who am I?</h1>
    <div class="container">
        <div class="imgarea left">
            <img src="aboutme.png" alt="profile in the about page" class="about-profile">
            <svg class="blob-shape" xmlns="http://www.w3.org/2000/svg" width="599" height="540" viewBox="0 0 599 540" fill="none">
                <path 
                    d="M589 246.5C547.464 432 468.788 540 320.5 540C172.212 540 0 377.275 0 208C0 38.7247 172.212 0 320.5 0C468.788 0 640.5 16.5 589 246.5Z" 
                    fill={activeTab === "general" ? "#EEDBD4" : activeTab === "qualification" ? "#BBB2AF" : "#E5C3C2"}
                />
            </svg>
        </div>
        <div class="textarea right">
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
                        <p>With a background in Nursing Science, I transitioned into tech after moving to the Netherlands for my relationship. I specialize in UX/UI design and front-end development, and I’m passionate about creating intuitive, user-centered digital experiences. I am continuously learning new technologies to enhance my skills and am currently focused on mastering modern front-end frameworks, as well as 3D web development tools like Three.js and React Fiber."</p>
                        <div class="general-info">

                        </div>
                    </div>
                {:else if activeTab === "qualification"}
                    <div data-state="active" class="active-qualification">
                        <h2>My journey is always accompanied by challenges</h2>
                        <div class="qualification-list">
                            <div class="education"></div>
                            <div class="experience"></div>
                        </div>
                    </div>
                {:else if activeTab === "skills"}
                    <div data-state="active" class="active-skills">
                        <h2>Skills I provide to create real-life impact</h2>
                    </div>
                {/if}
            </div>
        </div>
    </div>
</main>

<style>
    h1 {
        text-align: center;
        margin-bottom: 4rem;
    }

    .container {
        max-width: 90vw;
        margin: 0 auto;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    .right {
        margin: 0 auto; /* Ensure the fixed width of nav bar*/
    }

    .imgarea {
        position: relative;
        width: 36vw;
        height: 36vw;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-right: 3rem; /* Margin between left and right container */
    }
    

    .about-profile {
        width: 30vw;
        border-radius: 50%;
        position: absolute;
        top: 50%;
        left: 52%;
        transform: translate(-50%, -50%);
        z-index: 2;
    }

    .blob-shape {
        width: 36vw;
        position: absolute;
        top: 45%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 1;
    }

    .tablist {
        
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        border: 1px solid #463F3C;
        border-radius: 50px;
        padding: 0.25rem;
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

    .active-general, .active-qualification {
        max-width: 700px;
        margin: 3rem 0;
    }

    /* Font styling for h2 */
    h1 {
        margin-top: 0;
    }

    h2 {
        font-weight: 500;
        font-size: 1.7rem;
        text-align: center;
    }

    button {
        font-size: 1.1rem;

    }

    p {
        font-size: 1.1rem;
        line-height: 2;
    }
    /* Mobile responsive styles */
    @media (max-width: 994px) {
        .tablist, .imgarea {
            display: none;
        }
    }

</style>
