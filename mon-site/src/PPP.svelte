<script>
 import CV from '/public/CVs.pdf';
 import PPP from '/public/PPP.pdf';
</script>

<h1>Personal Professional Project </h1>
Here you can find my presentation : 
<div style="display: flex; justify-content: center; margin-top: 32px; margin-bottom: 8px;">
  <iframe
    title="Cv"
    src={PPP}
    width="768"
    height="432"
    style="border: 1px solid #ddd;"
    allow="autoplay"
  ></iframe>
</div>


<h2 style="text-align: left;">My CV : </h2>
<div style="display: flex; justify-content: center; margin-top: 32px; margin-bottom: 8px;">
  <iframe
    title="Cv"
    src={CV}
    width="735"
    height="1039"
    style="border: 1px solid #ddd;"
    allow="autoplay"
  ></iframe>
</div>

