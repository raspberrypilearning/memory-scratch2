## अनेक स्तर

अभी तक, खिलाड़ी को केवल पाँच रंगों का अनुक्रम याद रखना था। चलिए स्कोर, और कोड जोड़कर गेम में सुधार करें ताकि खिलाड़ी का स्कोर बढ़ने पर, याद रखने के लिए अनुक्रम की लंबाई बढ़ जाए।

+ `स्कोर`{:class="blockdata"} नामक नया वेरिएबल बनाएँ।

[[[generic-scratch-add-variable]]]

खिलाड़ी द्वारा याद रखने के लिए अनुक्रम की लंबाई के निर्णय के लिए `स्कोर`{:class="blockdata"} का उपयोग किया जाएगा। चलिए `3` के स्कोर (और अनुक्रम की लंबाई) के साथ आरंभ करें।

+ `स्कोर`{:class="blockdata"} को `3` पर सेट करने के लिए, अपने पात्र के `जब ⚑ क्लिक किया गया हो`{:class="blockevents"} कोड के आरंभ में ब्लॉक जोड़ें।

हमेशा पाँच रंगों का अनुक्रम बनाने के बजाय, अब आप अनुक्रम की लंबाई के लिए `स्कोर`{:class="blockdata"} चाहते हैं।

+ पात्र के `बार दोहराएं`{:class="blockcontrol"} लूप (अनुक्रम बनाने के लिए) को `स्कोर`{:class="blockdata"} बार दोहराने के लिए इसमें परिवर्तन करें:

```blocks
	(स्कोर) बार दोहराएं
end
	end
```

+ यदि अनुक्रम का अनुमान सही हो, तो आपको अगले अनुक्रम की लंबाई को बढ़ाने के लिए स्कोर में `1` जोड़ना चाहिए। जब आपको पता चले कि अनुक्रम का अनुमान सही है__ तो पात्र के कोड में __यह ब्लॉक जोड़ें।

```blocks
	[स्कोर v] से (1) बदले
```

--- hints ---
--- hint ---
`जीत` संदेश दिखाई देने पर आपको पता लग जाता है कि अनुक्रम का अनुमान सही है।
--- /hint ---
--- /hints ---

+ अंततः आपको कोड में `हमेशा के लिए`{:class="blockcontrol"} लूप जोड़ना होता है जो अनुक्रम बनाता है, ताकि प्रत्येक स्तर के लिए भिन्न अनुक्रम बनाया जाए। आपके पात्र का कोड कुछ इस प्रकार दिखाई देना चाहिए:

	```blocks
		जब ⚑ क्लिक किया गया हो
		[स्कोर v] पर [3] सेट करे
		हमेशा के लिए
end
			(सब v) का [क्रम v] मिटा दे
			(स्कोर) बार दोहराएं
end
				((1) से (4) तक क्रमरहित चुनने) से [क्रम v] जोङें
				पोशाक बदल कर ((last v) की [क्रम v] चीज) करें
				(1) सेकेंड तक ठहरे
			end
			<([क्रम v] की लंबाई) = [0]> होने तक ठहरे
			[won v] प्रसारण करें अौर रुके
			[स्कोर v] से (1) बदले
		end
	```

+ अपनी गेम का परीक्षण करने के लिए अपने मित्रों से कहिए। इससे पहले कि वे इसे खेलें, `क्रम`{:class="blockdata"} सूची को छिपाना याद रखें!
