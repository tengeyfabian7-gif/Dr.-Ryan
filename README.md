<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>VetCare Solutions — Online Pet Help</title>
<meta name="description" content="VetCare Solutions: Get expert veterinary advice for dogs, cats, birds, and small pets. Search common problems and find trusted solutions."/>
<style>
  body{margin:0;font-family:Arial,Helvetica,sans-serif;background:#f8fafc;color:#0f172a;}
  header{background:#2b8aef;color:white;padding:20px;text-align:center;}
  header h1{margin:0;font-size:28px;}
  header p{margin:6px 0 0;}

  .search-section{padding:20px;background:#fff;box-shadow:0 2px 6px rgba(0,0,0,0.08);}
  .search-box{display:flex;max-width:600px;margin:0 auto;}
  .search-box input{flex:1;padding:12px;border:1px solid #ddd;border-radius:8px 0 0 8px;font-size:16px;}
  .search-box button{padding:12px 20px;border:none;background:#2b8aef;color:white;font-weight:bold;border-radius:0 8px 8px 0;cursor:pointer;}

  main{max-width:1000px;margin:30px auto;padding:0 16px;}
  h2{margin-top:40px;}
  .solution{background:white;padding:18px;margin-bottom:18px;border-radius:12px;box-shadow:0 2px 6px rgba(0,0,0,0.06);}
  .solution h3{margin-top:0;color:#2b8aef;}
  .solution p{margin:6px 0;}

  footer{margin-top:40px;padding:20px;text-align:center;background:#f1f5f9;color:#555;font-size:14px;}
</style>
</head>
<body>

<header>
  <h1>🐾 VetCare Solutions</h1>
  <p>Your trusted online veterinary guide — find solutions to all your pet problems</p>
</header>

<section class="search-section">
  <form class="search-box" onsubmit="event.preventDefault(); searchSolutions();">
    <input type="search" id="query" placeholder="e.g. dog vomiting, cat not eating, bird feather loss..." />
    <button type="submit">Search</button>
  </form>
</section>

<main>
  <h2>Popular Pet Problems & Solutions</h2>

  <div id="results"></div>

  <div class="solution">
    <h3>Dog Vomiting</h3>
    <p><strong>Possible causes:</strong> dietary changes, infections, parasites, or ingestion of harmful substances.</p>
    <p><strong>Solution:</strong> Withhold food for 12 hours, give small amounts of water, then bland food. If vomiting persists or there is blood, consult a vet immediately.</p>
  </div>

  <div class="solution">
    <h3>Cat Not Eating</h3>
    <p><strong>Possible causes:</strong> dental pain, stress, infections, or systemic illness.</p>
    <p><strong>Solution:</strong> Offer wet food or warmed meals. If refusal lasts over 24 hours, see a vet — cats risk liver problems if they stop eating too long.</p>
  </div>

  <div class="solution">
    <h3>Bird Feather Loss</h3>
    <p><strong>Possible causes:</strong> molting, poor diet, parasites, or stress.</p>
    <p><strong>Solution:</strong> Ensure a balanced diet, provide enrichment, and check for mites. Persistent feather loss needs veterinary examination.</p>
  </div>

  <div class="solution">
    <h3>Rabbit Overgrown Teeth</h3>
    <p><strong>Possible causes:</strong> lack of fibrous diet leading to dental overgrowth.</p>
    <p><strong>Solution:</strong> Feed unlimited hay and chew toys. Severe cases require trimming by a vet.</p>
  </div>
</main>

<footer>
  © 2025 VetCare Solutions — For informational purposes only. Always consult a licensed veterinarian for emergencies.
</footer>

<script>
const SOLUTIONS = [
  { keyword: "dog vomiting", title:"Dog Vomiting", text:"Withhold food 12h, small water, bland diet. If persists or with blood → vet urgently."},
  { keyword: "cat not eating", title:"Cat Not Eating", text:"Offer wet/warm food. If >24h refusal, see vet — risk of liver disease."},
  { keyword: "bird feather loss", title:"Bird Feather Loss", text:"Balanced diet, enrichment, check parasites. Persistent loss → vet."},
  { keyword: "rabbit teeth", title:"Rabbit Overgrown Teeth", text:"Feed hay, chew toys. Severe overgrowth → vet trim."},
];

function searchSolutions(){
  const q = document.getElementById('query').value.toLowerCase();
  const results = document.getElementById('results');
  results.innerHTML = '';
  if(!q) return;

  const matches = SOLUTIONS.filter(s=> q.includes(s.keyword.split(" ")[0]) || q.includes(s.keyword.split(" ")[1]));
  if(matches.length===0){
    results.innerHTML = `<div class="solution"><h3>No direct match found</h3><p>Please consult your veterinarian for detailed advice.</p></div>`;
  } else {
    matches.forEach(m=>{
      results.innerHTML += `<div class="solution"><h3>${m.title}</h3><p>${m.text}</p></div>`;
    })
  }
}
</script>

</body>
</html>
