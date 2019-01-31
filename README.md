# Lightning-Component-VF
##### example using standard Lightning: library components in a visualforce page

#### lightning:helptext

##### Lightning App declaring dependencies
```html
<aura:application access="GLOBAL" extends="ltng:outApp" >
    <aura:dependency resource="lightning:helptext"/>
</aura:application>
```
##### Visualforce page implementing lighting:helptext binded to a span by ID
```html
<apex:page showHeader="true" sidebar="true">
	<apex:slds />
	<apex:includeLightning />
	
	<div style="border:3px dotted blue;width:200px;margin:30px;padding:50px;">
		
		Hello World <span id="testHelpText"></span>
		
	</div>

	<script>
		(function() {
			$Lightning.use("c:lcvfTest", function() {
				$Lightning.createComponent(
	                "lightning:helptext",
	                { content: 'Test helptext content goes here'},
	                "testHelpText",
	                function(cmp) {
	                    console.log("Component created!");
	                    console.log(cmp);
	            });
			});
		})();
    </script>
</apex:page>
```
##### Visualforce Page Demo
![Help Text Example](/helpTextExample.png?raw=true "Help Text Example")
