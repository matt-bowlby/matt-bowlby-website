<script lang="ts">
</script>


<div id="header">
    <div style="display:flex; align-items:center;">
        <div id="block"></div>
        <span style="font-weight: bold; user-select: none;">Matt Bowlby</span>
    </div>
    <div style="display:flex; gap:40px; align-items:center;">
        <button>Experience</button>
        <button>Projects</button>
        <button>Merits</button>
        <button>About Me</button>
        <button style="font-weight: bold;">Contact</button>
    </div>
</div>
<div id="frame" style="background: repeating-linear-gradient(135deg, #00000000, #00000000 40px, #ffffff01 40px, #ffffff01 60px);">

</div>
<div id="frame">

</div>


<style>
    #frame {
        width: 100%;
        height: 100vh;
    }
    #header {
        height:fit-content;
        /* background-color: inherit; */
        padding: 20px;
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        z-index: 10;
        /* box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); */
    }
    #block {
        width:20px;
        height:20px;
        background-color: var(--text-color);
        display:inline-block;
        margin-right:10px;
    }

    button {
        user-select: none;
        background: transparent;
        border: none;
        color: inherit;
        font-family: inherit;
        font-size: 1rem;
        cursor: pointer;
        padding: 5px;
        transition: opacity 0.2s;
    }
    button:hover {
        opacity: 0.7;
    }
</style>