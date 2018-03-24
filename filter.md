{%- assign courses = site.data.oer-curriculum-map | map: "course" | uniq -%}
{% capture subjects %}{% for sub in courses %}{{ sub | split: " " | first }}{% unless forloop.last %};{% endunless %}{% endfor %}{% endcapture %}
{% assign subjects = subjects | split: ";" | uniq %}

<div class="row mb-3">
<div class="col"><h2>Browse GEM Courses</h2></div>
    <div class="col"><div class="dropdown">
        <button class="btn btn-secondary dropdown-toggle float-right" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
            Filter by subject
        </button>
        <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
            <button class="dropdown-item filter active" type="button" id="all">Show all</button>
        {% for s in subjects %}
            <button class="dropdown-item filter" type="button" id="{{ s }}">{{ s }}</button>{% endfor %}
        </div>
    </div></div>
</div>

<div class="row justify-content-center" >
{% for course in courses %}
<!-- Button trigger modal -->
<div class="col-md-4 course {{ course | split: " " | first }}">
    <div class="card" data-toggle="modal" data-target="#course{{ forloop.index }}">
        <div class="card-header" >{{ course }}</div>
        <div class="card-body">
            <p class="card-text">Course description. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus. </p>
            <button type="button" class="btn btn-secondary" data-toggle="modal" data-target="#course{{ forloop.index }}">OERs</button>
        </div>
    </div>
    <!-- Modal -->
    <div class="modal fade" id="course{{ forloop.index }}" tabindex="-1" role="dialog" aria-labelledby="modalLabel{{ forloop.index }}" aria-hidden="true">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modalLabel{{ forloop.index }}">{{ course }}</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                {%- assign items = site.data.oer-curriculum-map | where: "course", course -%}
                <p><strong>Current text:</strong> {{ items[0].current-text }}</p>
                <p><strong>Current cost:</strong> {{ items[0].current-cost }}</p>
                <p><strong>OER Alternatives:</strong></p>
                <ul>
                {% for item in items %}
                <li><a href="{{ site.baseurl }}/browse/item.html?id={{ item.id | downcase }}">{{ item.opentext }}</a></li>
                {% endfor %}
                </ul>
                </div>
            </div>
        </div>
    </div>
</div>
{% endfor %}
</div>
<script>
    $(".filter").click(function() {
        var filterClass = $(this).attr("id");
        $(".filter").removeClass("active");
        $(this).addClass("active");
        if (filterClass == "all") {
            $(".course").show();
        }
        else {
            var test = "." + filterClass; 
            $(".course").hide();
            $(test).show();
        }
    });    
</script>