=== D8 to D7 backporting considerations

1. Change all instances of 'toolbar' to 'navbar'
1. Remove any PHP 'use' statements from the top of the navbar.module file.
1. Replace 'new Attribute()' with 'drupal_attributes()'
1. Add a widee breakpoint to navbar.install in hook_install.
1. Removed the breakpoing in hook_uninstall().
1. Alter the breakpoing retrieval code in navbar_pre_render() so that it uses breakpoints_breakpoint_load_all() instead of entities like in D8.
1. Change the references in navbar.js from 'module.navbar.wide' to just 'wide' for the breakpoint.
1. Change hook_library_info() to hook_library().
1. Remove the array('system', 'drupal') dependency from the navbar and navbar.menu libraries.
1. Add libraries for the matchemedia.js and debounce.js files from D8.
1. Change instances of 'drupalSettings' in JS files to 'Drupal.settings'.
1. Replace jQuery's .on() method with .live().
1. Implement hook_toolbar() on behalf of User and Shortcut modules.
