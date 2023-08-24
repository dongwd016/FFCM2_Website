---
layout: default
title: Model Validation
parent: Results
nav_order: 2
---

# Model Validation

The table lists the targets considered in FFCM-2 optimization. It is searchable by data type (column 1), the fuel (column 2). The **Details** tab provides the target specification and detailed validation comparisons of the trial and optimized FFCM-2 with the expeirmental data.

- Type: the types of optimization target data, they are
    - ign: shock tube ignition delay,
    - fls: laminar flame speed,
    - pro: shock tube speciation,
    - flw: flow reactor speciation,
    - lpb: low-pressure burner speciation
- Fuel: the fuel of a target data. In the current work, we only consider data for neat fuels as targets.
- Thermodynamic conditions for the target data is given by
  - Temperature, unit in Kelvins.
  - Pressure, unit in atm.
  - Equivalence ratio (pyrolysis targets do not have $\phi$ as equivalence ratio is undefined)
  - Mixture Composition: the composition of mixture, expressed by molar fraction.
- Experimental method: the experimental techniques used for the target data, e.g., spherical bomb measurements, or definition of ignition delay in shock tube experiments.

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.7.2/font/bootstrap-icons.css">
<link rel="stylesheet" href="https://unpkg.com/bootstrap-table@1.21.2/dist/bootstrap-table.min.css">
<!-- <link rel="stylesheet" type="text/css" href="extensions/filter-control/bootstrap-table-filter-control.css"> -->

<div class="table-responsive">
    <table
        id="table"
        data-toggle="table"
        data-show-toggle="true"
        data-search="true"
        data-height="950"
        data-strict-search="true"
        data-page-list="[25, 50, 100, All]"
        data-page-size="25"
        data-pagination="true"
        data-cookie="true"
        data-advanced-search="true"
        data-id-table="advancedTable"
        data-cookie-id-table="saveId"
        data-filter-control="true"
        data-filter-show-clear="true"
        data-show-search-clear-button="true"
        data-show-columns="true"
        data-show-columns-search="true"
        data-search-highlight="true"
        data-click-to-select="true"
        data-toolbar="#toolbar"
        data-escape="false"
        data-search-on-enter-key="false"
        data-show-filter-control-switch="true"
        data-url="{{ site.url }}{{ site.baseurl }}/assets/data/validation_table.json">
        <thead>
            <tr>
            <th data-field="Type" data-halign="center" data-align="center" data-filter-control="select">Type</th>
            <th data-field="Fuel" data-halign="center" data-align="center" data-filter-control="select">Fuel</th>
            <th data-field="Temp" data-halign="center" data-align="center">Temperature<br>$T$ (K)</th>
            <th data-field="Pres" data-halign="center" data-align="center">Pressure<br>$p$ (atm)</th>
            <th data-field="Phi" data-halign="center" data-align="center">Equivalence Ratio<br>$\phi$</th>
            <th data-field="Method" data-halign="center" data-align="center" data-width="300">Experimental<br>Method</th>
            <th data-field="Composition" data-halign="center" data-align="center" data-width="500">Mixture<br>Composition</th>
            <th data-field="url" data-formatter="linkFormatter" data-halign="center" data-align="center">Validation<br>Details</th>
            </tr>
        </thead>
    </table>
</div>

<script>
    $(function() {
      $('#table').bootstrapTable();
    })

    function linkFormatter(value, row) {
        return "<a href='" + row.url + "'>" + row.key + "</a>";
    }
</script>

<script src="https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
<script src="https://unpkg.com/bootstrap-table@1.21.2/dist/bootstrap-table.min.js"></script>
<script src="https://unpkg.com/bootstrap-table@1.21.2/dist/extensions/filter-control/bootstrap-table-filter-control.min.js"></script>
<script src="https://unpkg.com/bootstrap-table@1.21.2/dist/extensions/toolbar/bootstrap-table-toolbar.min.js"></script>
<script src="https://unpkg.com/bootstrap-table@1.21.2/dist/extensions/cookie/bootstrap-table-cookie.min.js"></script>
