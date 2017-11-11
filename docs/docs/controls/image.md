---
layout: default
title: The "image" control
slug: image
subtitle: Learn how to create controls using Kirki
mainMaxWidth: 50rem;
bodyClasses: control page
returns: string|array|int
---

The `image` control allows you create a control where users can upload images, or select images from their media-library.
You can choose how you want your data to be saved. By default the control saves the URL of the image as a string, but you have the ability to save the data as an `array( 'url', 'id', 'width', 'height' )` or as integer (image ID).

Examples:

```php

/**
 * Default behaviour (saves data as a URL).
 */
Kirki::add_field( 'kirki_demo', array(
	'type'        => 'image',
	'settings'    => 'image_setting_url',
	'label'       => esc_attr__( 'Image Control (URL)', 'kirki' ),
	'description' => esc_attr__( 'Description Here.', 'kirki' ),
	'section'     => 'image_section',
	'default'     => '',
) );

/**
 * Save data as integer (ID)
 */
Kirki::add_field( 'kirki_demo', array(
	'type'        => 'image',
	'settings'    => 'image_setting_id',
	'label'       => esc_attr__( 'Image Control (ID)', 'kirki' ),
	'description' => esc_attr__( 'Description Here.', 'kirki' ),
	'section'     => 'image_section',
	'default'     => '',
	'choices'     => array(
		'save_as' => 'id',
	),
) );

/**
 * Save data as array.
 */
Kirki::add_field( 'kirki_demo', array(
	'type'        => 'image',
	'settings'    => 'image_setting_array',
	'label'       => esc_attr__( 'Image Control (array)', 'kirki' ),
	'description' => esc_attr__( 'Description Here.', 'kirki' ),
	'section'     => 'image_section',
	'default'     => '',
	'choices'     => array(
		'save_as' => 'array',
	),
) );
```