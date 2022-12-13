<script src="https://YOUR-SERVER/javascripts/api/tableau-2.min.js"></script>
<div id="vizContainer"></div>
function initViz() {
    var containerDiv = document.getElementById("vizContainer"),
    url = "https://YOUR-SERVER/views/YOUR-VISUALIZATION";

    var viz = new tableau.Viz(containerDiv, url);
}
initViz();
