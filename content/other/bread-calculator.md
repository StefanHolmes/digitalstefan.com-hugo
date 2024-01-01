+++ 
draft = false           
date = 2023-12-31T23:27:32Z
title = "Bread Calculator"
description = ""
slug = ""
authors = ["Stefan Holmes"]
tags = []
categories = []
externalLink = ""
series = []
+++
{{< notice note >}}This page was recreated from the old version of this site, where it was just plain HTML, CSS and JS. I haven't fixed the formatting yet, but the calculator works just as it did.{{< /notice >}}
{{< rawhtml >}}
<script>
function calcBread() {
    // This isn't a great way to do this, but it works. 

    const flourRatio = document.querySelector("#flour_ratio").value
    const waterRatio = document.querySelector("#water_ratio").value
    const yeastRatio = document.querySelector("#yeast_ratio").value
    const saltRatio = document.querySelector("#salt_ratio").value
    const oilRatio = document.querySelector("#oil_ratio").value
    const flourWeight = document.querySelector("#flour_weight").value

    const flourConst = flourWeight / flourRatio

    document.querySelector("#water_calc").textContent = waterRatio * flourConst
    document.querySelector("#yeast_calc").textContent = yeastRatio * flourConst
    document.querySelector("#salt_calc").textContent = saltRatio * flourConst
    document.querySelector("#oil_calc").textContent = oilRatio * flourConst
}
</script>

<form>
    <fieldset>
        <legend>Adjust ratios</legend>
        <label>Flour
            <input type="number" id="flour_ratio" value="100" oninput="calcBread()">
        </label>
        <label>Water
            <input type="number" id="water_ratio" value="65" oninput="calcBread()">
        </label>
        <label>Yeast
            <input type="number" id="yeast_ratio" value="1" oninput="calcBread()">
        </label>
        <label>Salt
            <input type="number" id="salt_ratio" value="2" oninput="calcBread()">
        </label>
        <label>Oil
            <input type="number" id="oil_ratio" value="1.5" oninput="calcBread()">
        </label>
    </fieldset>
    <fieldset>
        <legend>How much flour, by weight?</legend>
        <label>Flour
            <input type="number" id="flour_weight" value="800" oninput="calcBread()">
        </label>
    </fieldset>
</form>

<table class="bread-table">
    <caption>Result:-</caption>
    <tr>
        <td>Water</td>
        <td id="water_calc"></td>
    </tr>
    <tr>
        <td>Yeast</td>
        <td id="yeast_calc"></td>
    </tr>
    <tr>
        <td>Salt</td>
        <td id="salt_calc"></td>
    </tr>
    <tr>
        <td>Oil</td>
        <td id="oil_calc"></td>
    </tr>
</table>
<script>calcBread()</script>
{{< /rawhtml >}}