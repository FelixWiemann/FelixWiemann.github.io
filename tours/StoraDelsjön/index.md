
<!--copied from https://www.w3schools.com/howto/howto_js_tabs.asp-->
<style>
/* Style the tab */
.tab {
    overflow: hidden;
    border: 1px solid #ccc;
    background-color: #f1f1f1;
    max-width: 1500px;
}

/* Style the buttons that are used to open the tab content */
.tab button {
    background-color: inherit;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    transition: 0.3s;
}
.nav{
    float: right !important; 
}

/* Change background color of buttons on hover */
.tab button:hover {
    background-color: #ddd;
}

/* Create an active/current tablink class */
.tab button.active {
    background-color: #ccc;
}

/* Style the tab content */
.tabcontent {
    display: none;
    padding: 6px 12px;
    border: 1px solid #ccc;
    border-top: none;
    background-image: url('map.svg');
    background-size: contain;
    background-origin: content-box;
    background-repeat: no-repeat;
    max-width: 1476px;
}
.createdwith{
    float: right;
    font-size: 9px;
}
</style>
<h1>StoraDelsjön</h1>
<div class="tab">
    <button class="tablinks" onclick="openMap(event, 'picture')" id="defaultOpen">Images</button>
    <button class="tablinks" onclick="openMap(event, 'elevation')">Elevation</button>
    <button class="tablinks" onclick="openMap(event, 'speed')">Speed</button>
    <button class="tablinks" onclick="openMap(event, 'leg')">Legs</button>
    <button class="nav" onclick="navBack(event)">Back</button>
</div>

<!-- Tab content -->
<div id="picture" class="tabcontent">
    <embed src="./picture.svg"/>
    <p class="createdwith">Maps created with <a href="https://www.openstreetmap.org/#map=12/57.6838755/12.0465305">OpenStreetMap</a> from 2024-04-24</p>
</div>

<div id="leg" class="tabcontent">
    <embed src="./legs.svg"/>
    <p class="createdwith">Maps created with <a href="https://www.openstreetmap.org/#map=12/57.6838755/12.0465305">OpenStreetMap</a> from 2024-04-24</p>
</div>

<div id="elevation" class="tabcontent">
    <embed src="./elevation.svg"/>
    <p class="createdwith">Maps created with <a href="https://www.openstreetmap.org/#map=12/57.6838755/12.0465305">OpenStreetMap</a> from 2024-04-24</p>
</div>
<div id="speed" class="tabcontent">
    <embed src="./speed.svg"/>
    <p class="createdwith">Maps created with <a href="https://www.openstreetmap.org/#map=12/57.6838755/12.0465305">OpenStreetMap</a> from 2024-04-24</p>
</div>

<p class="creation_date">created on: 2024-04-24</p>
<script>
    function navBack(evt){
        window.location.href = '..';
    }
    function openMap(evt, cityName) {
        // Declare all variables
        var i, tabcontent, tablinks;

        // Get all elements with class="tabcontent" and hide them
        tabcontent = document.getElementsByClassName("tabcontent");
        for (i = 0; i < tabcontent.length; i++) {
            tabcontent[i].style.display = "none";
        }

        // Get all elements with class="tablinks" and remove the class "active"
        tablinks = document.getElementsByClassName("tablinks");
        for (i = 0; i < tablinks.length; i++) {
            tablinks[i].className = tablinks[i].className.replace(" active", "");
        }

        // Show the current tab, and add an "active" class to the button that opened the tab
        document.getElementById(cityName).style.display = "block";
        evt.currentTarget.className += " active";
    }
    document.getElementById("defaultOpen").click();
</script> 