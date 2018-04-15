---
layout: default
title: Home
---

<div class="jumbotron">
    <div class="container">
        <h1 class="display-3">GH-Pages Collection</h1>
        <p>This is a basic Jekyll theme for building a simple, open digital collection using GitHub pages.</p>
        <p><a class="btn btn-primary btn-lg" href="{{ "/about/" | relative_url }}" role="button">Learn more &raquo;</a></p>
    </div>
</div>
<div class="container">
    <div class="row">
        <div class="col-md-6">  
            <div class="">
                <div class="card">
                    <div class="card-body">
                        <h3>Collection Basics</h3>
                        <p>This collection currently contains {{ items | size }} items, ranging in date from {{ date-range | first }} to {{ date-range | last }}. </p>
                        <p><a class="btn btn-secondary" href="{{ "/about/" | absolute_url }}" role="button">Learn more &raquo;</a></p>
                    </div>
                </div>
            </div>
            <div class="mt-2">
                <div class="card">
                    <div class="card-body">
                        <h3>Data</h3>
                        <p>The full descriptive metadata can be downloaded as a <a href="{{ "/data/metadata.csv" | absolute_url }}" target="_blank">CSV spreadsheet</a>, <a href="{{ "/data/metadata.json" | absolute_url }}" target="_blank">JSON</a>, or a <a href="{{ "/data/eodata.json" | absolute_url }}" target="_blank">GeoJSON</a> export. The data can be subsetted and downloaded as CSV or Excel from the <a href="{{ "/browse/" | relative_url }}" >browse table</a>.</p>
                        <p><a class="btn btn-secondary" href="{{ "/browse/" | relative_url }}" role="button">Browse &raquo;</a></p>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-6">
            <div class="card">
                <div class="card-body">
                    <h3>Locations</h3>
                    <p class="text-center"><a href="{{ "/map/" | relative_url }}"><img class="img-fluid rounded" src="{{ "/assets/images/iwdl-map.jpg" | relative_url }}" alt="IWDL map"></a></p>
                </div>
            </div>
        </div>
    </div>
</div>