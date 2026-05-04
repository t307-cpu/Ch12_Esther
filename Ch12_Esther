<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Plant Journey: Dispersal</title>
    <style>
        body { font-family: 'Segoe UI', sans-serif; background-color: #f1f8e9; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; }
        #game-container { background: white; padding: 2rem; border-radius: 15px; box-shadow: 0 10px 25px rgba(0,0,0,0.15); max-width: 600px; width: 100%; text-align: center; }
        #display-area { font-size: 4rem; margin: 20px 0; }
        #text-box { margin: 20px 0; line-height: 1.6; font-size: 1.2rem; color: #333; }
        button { display: block; width: 100%; padding: 12px; background-color: #2e7d32; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 1rem; margin: 8px 0; transition: 0.3s; }
        button:hover { background-color: #1b5e20; }
    </style>
</head>
<body>

<div id="game-container">
    <div id="display-area">🌱</div>
    <h2 id="title">The Journey Begins</h2>
    <div id="text-box">...</div>
    <div id="button-container"></div>
</div>

<script>
    const scenes = {
        seed: {
            title: "Dormant Seed", icon: "🌱",
            text: "You are a dormant seed. The soil is warm. Time to germinate!",
            options: [{ text: "Germinate", next: "mature" }]
        },
        mature: {
            title: "Mature Plant", icon: "🌻",
            text: "You are now fully grown! How will you make your 'babies'?",
            options: [
                { text: "Asexual (Clones)", next: "asexual" },
                { text: "Sexual (Seeds)", next: "sexual" }
            ]
        },
        asexual: {
            title: "Asexual Reproduction", icon: "🪴",
            text: "You choose Asexual Reproduction. This process involves <strong>mitotic cell division</strong>.  Because there is <strong>no fusion of gametes</strong>, your offspring are genetically identical (clones) to you. While efficient, this limits your genetic diversity.",
            options: [{ text: "Release Clones", next: "finish" }]
        },
        sexual: {
            title: "Sexual Reproduction", icon: "🌸",
            text: "You choose Sexual Reproduction. This involves the <strong>fusion of male and female gametes</strong> produced by <strong>meiosis</strong>. To proceed, you must ensure pollination. How will you pollinate?",
            options: [
                { text: "Self-Pollination", next: "SP"},
                { text: "Cross-Pollination", next: "CP" }
            ]
        },
        SP:{
            title: "Self-Pollination Reproduction", icon: "🌲",
             text:"You choose Self-Pollination (Same flower or same plant). This results in <strong>less genetic variation</strong>, which may limit the plant's ability to adapt to environmental changes.",
            options: [{ text: "Release Clones", next: "finish" }]
        },
        CP:{
            title: "Cross-Pollination", icon: "🌺",
            text: "You choose Cross-Pollination (Between different individuals). This results in <strong>greater genetic variation</strong>, increasing the chances of survival in changing environments.",
            options: [{ text: "Choose Dispersal Method for fertilization", next: "dispersal_choice" }]
        },
        fertilization: {
            title: "Fertilization", icon: "🌰",
            text: "The pollen tube grew through the style. The <strong>Ovule transformed into a Seed</strong>, and the <strong>Ovary ripened into a Fruit</strong>. Your babies are ready!",
            options: [{ text: "Conclusion", next: "conclusion" }]
        },
        // NEW DISPERSAL OPTIONS
        dispersal_choice: {
            title: "Select Dispersal Method", icon: "🌬️",
            text: "Your fruit is ripe. How will you move your seeds to a new home to avoid competition?",
            options: [
                { text: "Wind (Light seeds)", next: "disp_wind" },
                { text: "Water (Floating pods)", next: "disp_water" },
                { text: "Animal (Fleshy fruit)", next: "disp_animal" }
            ]
        },
        disp_wind: {
            title: "Wind Dispersal", icon: "💨",
            text: "You have developed lightweight seeds or wings (like a dandelion). They catch the breeze and drift far away, colonizing new ground.",
            options: [{ text: "fertilization", next: "fertilization"}]
        },
        disp_water: {
            title: "Water Dispersal", icon: "💧",
            text: "Your seeds are buoyant (like a coconut). They float down the river until they wash up on a distant shore, ready to sprout.",
            options: [{text: "fertilization", next: "fertilization" }]
        },
        disp_animal: {
            title: "Animal Dispersal", icon: "🐿️",
            text: "Your seeds are hidden in delicious fruit. An animal eats them, travels, and deposits them elsewhere (with natural fertilizer!).",
            options: [{ text: "fertilization", next: "fertilization" }]
        },
        finish: {
            title: "Survival Success!", icon: "🌳",
            text: "Your offspring have safely left the parent plant. They will now grow, avoid competition, and colonize new habitats. The cycle is complete!",
            options: [{ text: "Restart Cycle", next: "seed" }]
        },
        conclusion: {
            title: "Importance of Dispersal", icon: "💨💧🐿️",
            text: "Dispersal is vital for your species' survival for two main reasons:<br>1. <strong>To avoid overcrowding</strong> and <strong>competition</strong> for resources (light, water, minerals) with the parent plant.<br>2. <strong>To allow the species to colonize new habitats</strong>, expanding your territory and ensuring long-term survival.",
            options: [{ text: "Finish Journey", next: "finish"}]
        }
    };

    function go(sceneKey) {
        const scene = scenes[sceneKey];
        document.getElementById('title').innerText = scene.title;
        document.getElementById('display-area').innerText = scene.icon;
        document.getElementById('text-box').innerHTML = scene.text;
        
        const btnContainer = document.getElementById('button-container');
        btnContainer.innerHTML = '';
        
        scene.options.forEach(opt => {
            const btn = document.createElement('button');
            btn.innerText = opt.text;
            btn.onclick = () => go(opt.next);
            btnContainer.appendChild(btn);
        });
    }

    go('seed');
</script>
</body>
</html>
