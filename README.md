# XMLValidator

validateAndReturnError Incident

OVERVIEW

I need code to relate a schema (XSD file) to its XML document by putting a reference to the schema into the XML document.

It's notable that there are NSXMLDocument methods which can be used to setup validation using DTD files but there are no corresponding methods to setup validation using schema files.

I have a sample project, XMLValidator, that calls validateAndReturnError but it won't work with schema files because the XML document hasn't been given a reference to its schema. I NEED CODE TO DO THAT. 

I searched the web for a working example but I didn't find one.

INSTRUCTIONS TO REPRODUCE ISSUE

You use XMLValidator's Open command to open the XML file - either from XML/SCHEMA FILES/VALID folder or XML/SCHEMA FILES/ERROR folder - and XMLValidator then finds the XSD file with the same prefix in the same folder. Validation occurs in the MyDocument method readFromURL which calls validateAndReturnError for the file you opened.

I set a breakpoint at 

[doc validateAndReturnError:&error];

when it was hit, I could see that the document was read in and parsed by inspecting it's doc variable 

doc = (NSXMLDocument *) some-hex-value

but when you step into the validateAndReturnError method you just blow through to the next line and nothing happens. There is no error and no men left on base. Halp!

error  id  0x0  0x0000000000000000 
Just ignore the blank document that XMLValidator opens on launch.
