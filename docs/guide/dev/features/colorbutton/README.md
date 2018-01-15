---
category: authoring-content
order: 120
url: guide/dev_colorbutton
menu-title: Text and Background Color
meta-title-short: Text and Background Color
---
<!--
Copyright (c) 2003-2017, CKSource - Frederico Knabben. All rights reserved.
For licensing, see LICENSE.md.
-->

# Setting Text and Background Color

<info-box info="">
</info-box>

The optional [Color Button](https://ckeditor.com/cke4/addon/colorbutton) plugin provides the ability to define font and background color for text created in CKEditor. When enabled, it adds the **Text Color** and **Background Color** toolbar buttons that open a color selection drop-down list. If you want to quickly {@link guide/dev/features/removeformat/README remove colors} from your document, use the **Remove Format** button provided by the [Remove Format](https://ckeditor.com/cke4/addon/removeformat) plugin.

{@img assets/img/colorbutton_05.png The Text Color and Background Color features}

## More Colors Option and Color Dialog

You can also add the optional [Color Dialog](https://ckeditor.com/cke4/addon/colordialog) plugin which extends the color selector with the **More Colors** option and a user-friendly way to select the desired color through a dedicated **Select Color** dialog window. When this plugin is enabled, the **More Colors** option appears automatically for the text and background color.

{@img assets/img/colordialog_03.png The Select Color dialog window}

You can hide the **More Colors** feature by setting the {@linkapi CKEDITOR.config.colorButton_enableMore CKEDITOR.config.colorButton_enableMore} configuration option to `false`.

## Custom Color List

The list of colors available in the color selectors can be customized, for example to include the colors that are used in your website. You may also want to limit user's choice of colors to just selected few in order to avoid the overuse of colors.

Use the {@linkapi CKEDITOR.config.colorButton_colors CKEDITOR.config.colorButton_colors} configuration option to define a custom list available in the **Text Color** and **Background Color** features. For example:

	config.colorButton_colors = 'CF5D4E,454545,FFF,CCC,DDD,CCEAEE,66AB16';

Additionally, since CKEditor 4.5.8 you can also disable the "Automatic" option by setting the {@linkapi CKEDITOR.config.colorButton_enableAutomatic CKEDITOR.config.colorButton_enableAutomatic} option to `false`.

	config.colorButton_enableAutomatic = false;

These settings will cause the color list to only contain the seven colors listed above, with no "Automatic" option available:

{@img assets/img/colorbutton_04.png The customized color list}

<info-box hint="">
</info-box>

## Custom Color Style Definition

You can also decide how the color definition is stored by setting the {@linkapi CKEDITOR.config.colorButton_foreStyle CKEDITOR.config.colorButton_foreStyle} (for text color) and {@linkapi CKEDITOR.config.colorButton_backStyle CKEDITOR.config.colorButton_backStyle} (for background color) configuration options. By default, the color is added as a `<span>` element with the `style` attribute, but you could also e.g. use the legacy (and not recommended) HTML4 `<font>` element definition:

	config.colorButton_foreStyle = {
		element: 'font',
		attributes: { 'color': '#(color)' }
	};

	config.colorButton_backStyle = {
    	element: 'font',
    	styles: { 'background-color': '#(color)' }
	};

CKEditor will then output the color definition as `<font>` elements with `color` and `style="background-color"` attributes for text and background color, respectively:

	<p><font color="#800080">This is my text color.</font><br/>
	<font style="background-color:#FFFF00;">This is my background color</font></p>

## Text and Background Color Demo

See the [working "Setting Text and Background Color" sample](https://sdk.ckeditor.com/samples/colorbutton.html) that showcases the usage and customization of the text and background color features.

## Related Features

Refer to the following resources for more information about text styling and formatting:

* The {@link guide/dev/features/copyformatting/README Using the Copy Formatting Feature} article explains how to copy text formatting between document fragments.
* The {@link guide/dev/features/removeformat/README Removing Text Formatting} article explains how to quickly remove any text formatting that is applied through inline HTML elements and CSS styles.
* The {@link guide/dev/features/basicstyles/README Basic Text Styles: Bold, Italic and More} article explains how to apply bold, italic, underline, strikethrough, subscript and superscript formatting.
* The {@link guide/dev/features/styles/README Applying Styles to Editor Content} article discusses creating more semantically correct text styles.
* The {@link guide/dev/features/format/README Applying Block-Level Text Formats} article presents how to apply formatting to entire text blocks and not just text selections.
</font></font></span>