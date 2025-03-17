<script>
    let activeTab = "general"; // 기본적으로 "general" 탭이 활성화됨
</script>

<main>
    <h1>Who am I?</h1>
    <div class="container">
        <div class="imgarea">
            <img src="aboutme.png" alt="profile in the about page" class="about-profile">
            
            <!-- SVG 색상 변경 -->
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
                    </div>
                {:else if activeTab === "qualification"}
                    <div data-state="active" class="active-qualification">
                        <h2>My journey is always accompanied by challenges</h2>
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
        margin: 0 auto;
    }
    
    .textarea {
        min-width: 536px;
        margin: 0 auto;
    }

    .imgarea {
        position: relative;
        width: 36vw;
        height: 36vw;
        display: flex;
        align-items: center;
        justify-content: center;
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

    .tablist > button {
        border: none;
        background-color: transparent;
        width: 170px;
        margin: 0 auto;
        padding: 1.5rem 0;
        transition: background-color 0.5s ease;
    }

    .tablist {
        border: 1px solid #463F3C;
        border-radius: 50px;
        padding: .25rem .5rem;
    }

    /* 탭 버튼 활성화 시 색상 변경 */
    .tablist button.active {
        border-radius: 50px;
    }

    /* 탭 버튼 hover 시 색상 변경 */
    .tablist button:hover {
        background-color: transparent; /* Default fallback */
    }


    h1 {
        margin-top: 0;
    }

    h2 {

        font-weight: 500;
        text-align: center;

    }

    button {
        font-size: 1.3rem;
        text-align: center;
    }

    @media (max-width: 994px) {
        .tablist, .imgarea {
            display: none;
        }
    }
</style>
