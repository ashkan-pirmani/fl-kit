---
title: Federated Learning Glossary
contributors: [Ashkan Pirmani]
page_id: fl_glossary
search_exclude: false
toc: false
---
Terminology in Federated Learning can be complex and context-specific. The glossary presents clear, concise definitions of key concepts and technical terms to ensure conceptual clarity and promote consistent understanding across disciplines.

**Interactive Glossary Table**

<div class="glossary-table-toolbar">
  <div class="toolbar-group" id="datatable-search-control"></div>
  <div class="toolbar-group">
    <label for="category-filter">Filter by Category:</label>
    <select id="category-filter">
      <option value="">All</option>
      <option value="Federated Learning">Federated Learning</option>
      <option value="Bioinformatics">Bioinformatics</option>
      <option value="Data & Privacy">Data & Privacy</option>
      <option value="General ML">General ML</option>
      <option value="Clinical/Healthcare">Clinical/Healthcare</option>
      <option value="Analytics">Analytics</option>
      <option value="Security/Privacy">Security/Privacy</option>
    </select>
  </div>
  <div class="toolbar-group" id="datatable-length-control"></div>
</div>

<div class="glossary-table-container">
  <table id="glossary-table">
    <thead>
      <tr>
        <th>Term</th>
        <th>Description</th>
        <th>Category</th>
      </tr>
    </thead>
    <tbody>
      {% for item in site.data.glossary %}
      <tr>
        <td>{{ item.term }}</td>
        <td>{{ item.description }}</td>
        <td><span class="badge-category" data-category="{{ item.category }}">{{ item.category }}</span></td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<link rel="stylesheet" href="https://cdn.datatables.net/1.13.4/css/jquery.dataTables.min.css">
<style>
:root {
  --flkit-bg: #f8f9fa;
  --flkit-toolbar: #f5f6fa;
  --flkit-border: #e0e0e0;
}
.glossary-table-toolbar {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 1.5em;
  margin-bottom: 1.2em;
  background: var(--flkit-toolbar);
  border-radius: 10px;
  padding: 1em 1.5em;
  box-shadow: 0 2px 8px rgba(0,0,0,0.03);
  border: 1px solid var(--flkit-border);
}
.toolbar-group {
  display: flex;
  align-items: center;
  gap: 0.7em;
}
#category-filter {
  padding: 0.4em 1em;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 1em;
  background: var(--flkit-bg);
}
.dataTables_filter {
  margin-bottom: 0 !important;
}
.dataTables_filter input[type="search"] {
  font-size: 1.08em;
  padding: 0.5em 1.2em;
  border-radius: 8px;
  border: 1px solid #bbb;
  margin-left: 0.5em;
  font-weight: 500;
  width: 260px;
  max-width: 100%;
  background: var(--flkit-bg);
}
.dataTables_filter label {
  font-size: 1.08em;
  font-weight: 600;
}
.dataTables_length select {
  font-size: 1.05em;
  border-radius: 8px;
  padding: 0.3em 0.7em;
  background: var(--flkit-bg);
}
.glossary-table-container { width: 100%; padding: 0; background: none; border-radius: 0; }
#glossary-table { font-size: 1.08em; width: 100%; box-shadow: 0 4px 24px rgba(0,0,0,0.07); border-radius: 12px; overflow: hidden; }
#glossary-table thead th { background: #f5f6fa; color: #22223b; font-weight: 700; font-size: 1.12em; border-bottom: 2px solid #e0e0e0; padding: 14px 12px; position: sticky; top: 0; z-index: 2; }
#glossary-table td { padding: 14px 10px; vertical-align: middle; font-size: 1.06em; }
#glossary-table tbody tr:nth-child(even) { background: #f8f9fa; }
#glossary-table tbody tr:hover { background: #e3f2fd; transition: background 0.2s; }
.badge-category { display: inline-block; padding: 0.25em 0.9em; border-radius: 12px; background: #e0e7ef; color: #234; font-size: 0.97em; font-weight: 600; letter-spacing: 0.01em; margin-right: 2px; }
.badge-category[data-category="Federated Learning"] { background: #e0f7fa; color: #00796b; }
.badge-category[data-category="Bioinformatics"] { background: #f3e5f5; color: #6a1b9a; }
.badge-category[data-category="Data & Privacy"] { background: #fff3e0; color: #e65100; }
.badge-category[data-category="General ML"] { background: #e3f2fd; color: #1565c0; }
.badge-category[data-category="Clinical/Healthcare"] { background: #fce4ec; color: #ad1457; }
.badge-category[data-category="Analytics"] { background: #e8f5e9; color: #388e3c; }
.badge-category[data-category="Security/Privacy"] { background: #ede7f6; color: #4527a0; }
@media (max-width: 900px) {
  .glossary-table-toolbar { flex-direction: column; align-items: stretch; gap: 1em; }
  .toolbar-group { width: 100%; justify-content: flex-start; }
  .dataTables_filter input[type="search"] { width: 100%; }
}
</style>
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script src="https://cdn.datatables.net/1.13.4/js/jquery.dataTables.min.js"></script>
<script>
  $(document).ready(function() {
    var table = $('#glossary-table').DataTable({
      "paging": true,
      "info": false,
      "autoWidth": false,
      "stripeClasses": ['odd-row', 'even-row'],
      "language": {
        "searchPlaceholder": "Search glossary terms...",
        "search": ""
      },
      "dom": '<"datatable-toolbar-row"lfrtip>'
    });
    // Move DataTables controls into custom toolbar in new order
    $("#datatable-search-control").append($(".dataTables_filter"));
    $("#datatable-length-control").append($(".dataTables_length"));
    // Category filter
    $('#category-filter').on('change', function(){
      table.column(2).search(this.value).draw();
    });
  });
</script>


