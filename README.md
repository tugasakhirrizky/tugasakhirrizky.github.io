<script src="https://www.example.com/javascripts/api/tableau-2.js"></script>
<div id="tableauViz"></div>

function initializeViz() {
var placeholderDiv = document.getElementById("tableauViz");
var url = "http://public.tableau.com/views/WorldIndicators/GDPpercapita";
var options = {
 width: '600px',
 height: '600px',
 hideTabs: true,
 hideToolbar: true,
 };
viz = new tableau.Viz(placeholderDiv, url, options);
}
