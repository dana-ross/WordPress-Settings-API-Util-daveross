Introduction
------------

WordPress 2.7 added a handy API for plugin and theme developers to build configuration forms. It eliminates much of the hassle experienced when building forms from scratch, but it could go further. It's not the most user-friendly API in the world.

This project provides a set of classes to help build basic forms -- what most of us need -- without having to deal with the Settings API directly.

Just add Settings_API_Util.inc to your plugin or theme and include() the file in your PHP code.

License
-------

New BSD license: http://www.opensource.org/licenses/BSD-3-Clause

Use it to make beautiful things.

Usage
-----

Creating a form:

`// Unique ID for this form
$formID = 'example';

// Name which options will be stored under in the WordPress options table
$optionsName = 'example_options';

$form = Settings_API_Util::forID($formID, $optionsName);`

Add a section:

`$newSection = $form->addSection('section_id', 'Section Title');`

Add fields to the new section:

`$newField = $newSection->addField('field_id', 'Field Label', Settings_API_Util_Field::TYPE_TEXTFIELD);`

Render the form:

`// Get a reference to the form we created above
$form = Settings_API_Util::forID('example');
// Output the form
$form->renderBasicForm('Form Title', Settings_API_Util::ICON_SETTINGS);`

Of course, actually integrating all this is more complicated. I've found the best approach is to create the form, sections, and fields in your admin_init hook, and render the form in your admin_menu hook.

Acknowledgements
----------------

"If I have seen a little further it is by standing on the shoulders of Giants."

Otto's [WordPress Settings API Tutorial][http://ottopress.com/2009/wordpress-settings-api-tutorial/] cleared up a lot of my confusion with the Settings API.

All my friends and co-workers at Straight North, the [Chicago Internet Marketing Firm][http://www.straightnorth.com/] that works and plays hard.

[Queso Broso][http://www.quesa-broso.com/], who keep us well-fed.


