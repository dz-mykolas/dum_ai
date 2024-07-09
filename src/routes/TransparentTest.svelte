<script lang="ts">
    import { appWindow } from '@tauri-apps/api/window';
    async function addDecorations() {
        try {
            await appWindow.setDecorations(true);
            console.log("Decorations added");
        } catch (error) {
            console.error("Failed to add decorations:", error);
        }
    }

    addDecorations();
</script>

<div class="container">
    <a href="/test1">
        <button class="navigateButton">Test 1</button>
    </a>
    <a href="/test2">
        <button class="navigateButton">Test 2</button>
    </a>
    <a href="/dd">
        <button class="navigateButton">DD</button>
    </a>
    <h1>Transparent Window Test</h1>
    <div class="transparent-area">
        This area is transparent
    </div>
    <div class="semi-transparent-area">
        This area is semi-transparent
    </div>
    <div class="opaque-area">
        This area is opaque
    </div>
</div>

<style>
:global(body) {
    margin: 0;
    padding: 0;
    background: rgba(0, 0, 0, 0);
    font-family: Arial, sans-serif;
}

.container {
    padding: 20px;
}

h1 {
    color: #333;
}

.transparent-area, .semi-transparent-area, .opaque-area {
    padding: 20px;
    margin: 10px 0;
    border-radius: 5px;
}

.transparent-area {
    background: transparent;
    border: 2px solid #333;
    color: #333;
}

.semi-transparent-area {
    background: rgba(100, 100, 100, 0.5);
    color: white;
}

.opaque-area {
    background: #4CAF50;
    color: white;
}
</style>
