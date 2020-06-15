# Doxygen Multi-Version Selection

This tool allows client-side selection of different versions of the same Doxygen page.
It provides a drop-down menu, displaying all available versions. Only those versions
become links that feature the current page; all others are grayed out and marked with
strike-though, to signal that the version did not yet (or does not anymore) offer that class.

![Example](https://raw.githubusercontent.com/root-project/doxyvers/img/doxyvers.png)

To use, add to the end of the `<head>`:
```html
<!-- BEGIN version select -->
<link rel="stylesheet" type="text/css" href="../dropdown.css">
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js">
</script>
<!-- END version select -->
</head>
```
and somewhere in the doxygen HTML header ( `titlearea`) where you'd traditionally display the software version of the doxygen documentation (`$projectnumber`):
```html
<!-- BEGIN version select -->
<div class="dropdown">
   <button class="dropbtn">Version $projectnumber</button>
   <div class="dropdown-content">
   </div>
</div>
<script type="text/javascript" src="../selectversion.js"></script>
<!-- END version select -->
```

This tool assumes that the doxygen documentation for all versions has a common and
browsable ("index"-able) parent directory containing the files of this repository.

See the top of `selectversion.js` for configuration options, and adjust the style / colors / 
width in `dropdown.css`.
