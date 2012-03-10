# Textastic Customization Files

## Templates

Template files are located in the *Templates* subdirectory. 

### File Format 

Textastic templates are simple JSON files with the following format:

```json
{
	"uuid": "74C6D420-A016-4659-AF92-B5CCC1AE53BB",
	"category": "HTML",
	"templates": [
		{
			"name": "HTML5",
			"fileExtension": "html",
			"snippet": "<!DOCTYPE HTML>\n<html>\n<head>\n<meta charset=\"utf-8\">\n<title>${1:untitled}<\/title>\n<\/head>\n\n<body>$0\n<\/body>\n<\/html>"
		}
	]
}
```

* `uuid`: uniquely identifies the template file
* `category`: the category under which the templates in this file appear in the the template selection view
* `templates`: contains an array of code templates
  * `name`: the name under which this template appears in the template selection view
  * `fileExtension`: the file extension that is automatically added to the file name when the user selects this template
  * `snippet`: The snippet that is inserted after the file is created. Be sure to escape new line and tab characters with \n and \t. 
  
        Always use tab characters for indentation - if necessary, Textastic will replace them with space characters depending on the current settings. 
        
        Have a look at the [TextMate manual entry on snippets](http://manual.macromates.com/en/snippets) for an overview of the snippet syntax. Textastic supports tab stops, placeholders, mirrors and transformations. 
    
        Currently, only the `$UUID` variable is supported. It automatically creates a new uuid and inserts it.
        
### Creating new templates

If you want to create a new template, create a UTF-8 .json file in the *"#Textastic/Templates"* folder in Textastic and choose the template called "Template" in the "Textastic" category. 

This will automatically create a new template file with a new uuid. Use the tab key to go from tab stop to tab stop and enter the necessary information. Be sure to save the template in the "#Textastic/Templates" folder or it will not be loaded by Textastic.

*Note*: you can also manually create uuids using the `uuidgen` terminal command on Mac OS X.

### Modifying existing templates

If you want to modify existing templates, you can get the template files from this repository, edit them and put the modified files in the *"#Textastic/Templates"* folder. Textastic will pick up the changes immediately when you open the template selection view in the file creation dialog. 

It is important that you do not change the uuid, so that your custom files will be used instead of the built-in ones with the same uuid. This behavior is the same as for custom syntax definitions as explained [in the manual](http://www.textasticapp.com/v4/manual/lessons/How_can_I_add_my_own_syntax_definitions__themes_and_templates.html).

## Code Completion

All code completion files are located in the *CodeCompletion* subdirectory. 

If you want to modify code completion definitions, you can edit them and put them in the *"#Textastic/CodeCompletion"* folder. Textastic will pick up the changes *at application startup time*, so you have to manually quit the app. If you do not change the uuid, your custom files will be used instead of the built-in ones. This behavior is the same as for custom syntax definitions as explained [in the manual](http://www.textasticapp.com/v3/manual/lessons/How_can_I_add_my_own_syntax_definitions_and_themes.html).

*TODO: document file format*

## License

Textastic customization files in this repository are released under the MIT license (see the LICENSE file).

## Contact / Bugs / Features

If you want to add or modify templates or code completion files to Textastic, I happily accept pull requests. If they are useful to a broad audience, I will add them to future version of Textastic.

For more contact options and the feedback forum, please visit the [Textastic website](http://www.textasticapp.com/).