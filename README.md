##jsonA ( arrayValues)```/**
 * =====================================
 * jsonA ( arrayValues )
 *
 * RETURNS:
 *		wraps the items in "[" and "]" removes trailing coma
 *
 * PARAMETERS:
 *		arrayValues = a series of items created with the cf jsonItem
 *
 * DEPENDENCIES:
 *		None
 *
 * HISTORY:
 *		MODIFIED on 2015-JAN-24 Todd Geist, todd@geistinteractive.com
 *			changed the name to jsonA( arrayValues )
 *		MODIFIED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			changed the name to jsonNewArray ( arrayValues )
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonAv ( value)```/**
 * =====================================
 * jsonAv( value )
 *
 * RETURNS:
 *		prepares a string for inclusion as an element in a JSON array
 *
 * PARAMETERS:
 *		value = string - the value of the Array element
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-JAN-24 Todd Geist, todd@geistinteractive.com
 *			changed the name to jsonAv( arrayValues )
 *		MODIFIED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			changed name to jsonNewArrayValue ( value )
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonDelete ( json;keyOrIndex)```/**
 * =====================================
 * jsonDelete ( json ; keyOrIndex )
 *
 * RETURNS:
 *		JSON Object with the specified property removed
 *
 * PARAMETERS:property
 *		json  -  the valid JSON string to modify
 *		keyOrIndex -  the key of the property to remove or the index to remove of an array
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 *		MODIFIED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			changed the name to "jsonDelete ( json ; keyOrIndex )" and added support for handling an array
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonGet ( json;keyOrIndexOrPath)```/**
 * =====================================
 * jsonGet ( json ; keyOrIndexOrPath )
 *
 *  a convenience function that handles the most comm JSONPath cases
 *  Works with JSON Objects and JSON Arrays
 *
 * RETURNS:
 *             the value specfied by the keyOrIndex
 *
 * PARAMETERS:
 *             json - the json string
 *             keyOrIndex - use a "key" for objects, and an "index" for number
 *
 * DEPENDENCIES:
 *             BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *             MODIFIED on 2015-APR-21 Daniel Smith, dansmith65@gmail.com
 *                     save error message to $json.error and clear the variable if no error
 *                     return "?" on error
 *             MODIFIED on 2015-FEB-08 Todd Geist, todd@geistinteractive.com
 *                     changed parameter name to "keyOrIndexOrPath"
 *             CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonGetKeyList ( json)```/**
 * =====================================
 * jsonGetKeyList ( json )
 *
 *   gets the list of member properties from a JSON object.  It only goes one level deep
 *
 * RETURNS:
 *		the list of property names
 *
 * PARAMETERS:
 *		json  -  the valid JSON string to get the properties from
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 *		MODIFIED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			changed name to jsonGetKeyList ( json )
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonGetValueList ( json)```/**
 * =====================================
 * jsonGetValueList ( json )
 *
 *   gets the Values of an object or array one level deep
 *
 * RETURNS:
 *		a list of values. JSON Objects and Arrays are returned as JSON
 *
 * PARAMETERS:
 *		json  -  the valid JSON string to get the properties from
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		CREATED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonMerge ( target;source)```/**
 * =====================================
 * jsonMerge ( target ; source )
 *
 *	does a shallow merge of all properties on the source into the target
 *	shallow means that it does not traverse nested properties.
 *	Only the objects immediate own properties are dealt with
 *
 * RETURNS:
 *		the modifed JSON Object
 *
 * PARAMETERS:
 *		source -  the valid JSON string to merge into
 *		target -  the valid jsson to copy from
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 *		CREATED on 2015-FEB-03 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonModify ( json;keyOrIndexOrPath;newValue)```/**
 * =====================================
 * jsonModify ( json ; keyOrIndexOrPath ; newValue )
 *
 *   adds or modifies a property on a JSON Object
 *
 * RETURNS:
 *		the modifed JSON Object
 *
 * PARAMETERS:
 *		json -  the valid JSON string modify
 *		keyOrIndexOrPath -  the name of the object property, or array index to add or modify
 *			or the json Path to the property array you want to modify
 *			ex: 'jsonModify($json; "invoice.line[2]qty" ; 2)' would set the "qty" property
 *			on the 3rd object on the "Line" array to 2.  All inbetween props are created as necessary
 *						
 *		newValue -  the value of the property or array item
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 * 		Modified on 2015-APR-19 Todd Geist, todd@geistinteractive.com
 * 		 	added error now return "?", actual error is in $json.error
 * 		Modified on 2015-FEB-03 Todd Geist, todd@geistinteractive.com
 * 		 	added the ability to use JSONPath as the keyOrIndexOrPath
 * 		Modified on 2015-JAN-26 Todd Geist, todd@geistinteractive.com
 * 		 	fixed a bug in handling "" as a newValue
 *		MODIFIED on 2015-JAN-24 Todd Geist, todd@geistinteractive.com
 * 		 	changed name to jsonModify ( json ; property ; value )
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonO ( properties)```/**
 * =====================================
 * jsonO( properties )
 *
 *   wraps and prepares a series of jsonObjectMembers for inclusion in a JSON Object
 *
 * RETURNS:
 *		the json Object
 *
 * PARAMETERS:
 *		properties - a series of json object properties created by the cf jsonNewObjectProperty
 *
 * DEPENDENCIES:
 *		None
 *
 * HISTORY:
 *		MODIFIED on 2015-JAN-24 Todd Geist, todd@geistinteractive.com
 *			changed the name to jsonO( properties )
 *		MODIFIED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			changed name to jsonNewObject ( properties )
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonOp ( key;value)```/**
 * =====================================
 * jsonOp ( key ; value )
 *
 *   Formats a key value pair as an JSON object property
 *
 * RETURNS:
 *		the key value pair
 *
 * PARAMETERS:
 *		key  -  the name of the property
 *		value = string - the value of the Array element
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-JAN-24 Todd Geist, todd@geistinteractive.com
 *			changed the name to jsonOp ( key ; value )
 *		CREATED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 * 			changed name to jsonNewObjectProperty ( key ; value )
 * 		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonPrettyPrint ( json;whiteSpace)```/**
 * =====================================
 * jsonPrettyPrint ( json ; whiteSpace )
 *
 *   Pretty Prints a json Object with an indent.
 *
 * RETURNS:
 *		the prettified JSON Object
 *
 * PARAMETERS:
 *		json - the json string to pretty print
 *		whiteSpace - string - the character or characters to use as whiteSpace
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 *		MODIFED on 2015-JAN-07 Todd Geist, todd@geistinteractive.com
 *			added second parameter to set the white space character
 *		CREATED on 2015-JAN-06 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```##jsonValidate ( json)```/**
 * =====================================
 * jsonValidate ( json )
 *
 *   validates a JSON String
 *
 * RETURNS:
 *		1 if valid, and an error string if invalid. the errorString will equal FALSE
 *
 * PARAMETERS:
 *		json - the json string to validate
 *
 * DEPENDENCIES:
 *		BaseElements Plugin version 3.0 or greater
 *
 * HISTORY:
 *		MODIFIED on 2015-APR-21 Todd Geist, todd@geistinteractive.com
 * 			return "?" on error and the actual Error is set into $json.error
 *		MODIFIED on 2015-APR-19 Todd Geist, todd@geistinteractive.com
 *		CREATED on 2015-JAN-08 Todd Geist, todd@geistinteractive.com
 *
 * =====================================
 */```