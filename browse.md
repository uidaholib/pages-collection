---
layout: table
title: Browse
---
{% assign items = site.data.metadata %}

## Browse Items

This table provides sorting and basic search of the archive contents. 
Click on the "Read" link to see the full document.

<table id="item-table">
    <thead>
        <tr>
            <th>Title</th>
            <th>Date</th>
            <th>Subjects</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td><a href="{{ site.baseurl }}/browse/item.html?id={{ item.indexid }}">{{ item.title }}</a></td>
            <td>{{ item.date }}</td>
            <td>{{ item.subject }}</td>
            <td>{{ item.description | truncatewords: 15 }} <a href="{{ site.baseurl }}/items/{{ item.identifier | downcase }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>
