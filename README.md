# XMLValidator

validateAndReturnError Incident

OVERVIEW

I need code to relate a schema (XSD file) to its XML document by putting a reference to the schema into the XML document.

It's notable that there are NSXMLDocument methods which can be used to setup validation using DTD files but there are no corresponding methods to setup validation using schema files.

I have a sample project, XMLValidator, that calls validateAndReturnError but it won't work with schema files because the XML document hasn't been given a reference to its schema. I NEED CODE TO DO THAT. 

I searched the web for a working example but I didn't find one.

INSTRUCTIONS TO REPRODUCE ISSUE

You use XMLValidator's Open command to find the XML file and XMLValidator then finds the XSD file with the same prefix in the same folder. Validation occurs in the MyDocument method readFromURL which calls validateAndReturnError for the file you opened.

There are 2 pairs of documents. One pair is in the XML_SCHEMA/VALID folder. This pair should validate successfully. The other pair is in the XML_SCHEMA/ERROR folder. This pair should fail validation, returning an error object. Note that these files are local, not web based.

XMLValidator was built in Mojave 10.14.3 with Xcode 10.1. (I can't upgrade because I don't have 15 GB of space.)

Just ignore the blank document that XMLValidator opens on launch.
