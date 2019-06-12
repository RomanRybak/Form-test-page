# Form-test-page

#this is a small tutorial I did for my coworker who was going to help me work with forms, I included details on how to work with different tags inlcuding one purposeful error for him to detect




<script src="https://portalpro.suffolk.edu/forms1util.js?v=14" type="text/javascript"></script>  <!-- Required-->

<div class="error_box inactive"></div>  <!-- Required-->

<form name="main_form" method="post" action="#" novalidate> <!-- replace action="whatever" with action="#", delete onsubmit="whatever" if there's any, write novalidate -->
    <input name="form_id" type="hidden" value="192683">
    <input name="form:names" type="hidden" value="&amp;form_id&amp;form:names&amp;_your_first_name&amp;First Name&amp;Middle Initial&amp;Last Name&amp;Email&amp;Address Line One&amp;Address Line Two&amp;City&amp;State&amp;Country&amp;Zip&amp;Class Year&amp;Prepare a Letter Stating&amp;Additional Information&amp;Student ID&amp;Home Phone&amp;Work Phone&amp;Name&amp;Address Line One_2&amp;Address Line Two_2&amp;City_2&amp;State_2&amp;Country_2&amp;Zip_2&amp;Letter is to be&amp;scaptcha_response&amp;&amp;submit&amp;">
    <!--HIDDEN INPUT, Needed to protect against SPAM!-->
	
	<div class="info"><em>Required fields are marked with an asterisk (*)</em></div> <!-- most pages will have this-->
	
	
<fieldset> <!--mainly used for accessibility reasons-->
	 
	<legend>Test page subheading</legend> <!--not all pages will have this-->
	
	
    <div class="form_row">																												<!-- this is a typical text field-->
        <div class="label">
            <label for="FirstName">First Name:<span class="su_required" title="This is a required field">*</span></label>           <!-- typical way to go around first name, last name would be very similar if needed-->
		</div>               
        <div class="input">
            <input type="text" id="FirstName" name="FirstName" placeholder="E.g. John " required="" autofocus="">     <!--remember each field must have its OWN id, can't have both first and last name ids be "name" for example-->
        </div>                                                  <!-- placeholder field is not required and is only there to assist the user-->
    </div>														<!-- required="" field should only be there if the field First Name is required -->
	
	
	
	<!--   This piece of code on line 20 <span class="su_required" title="This is a required field">*</span> means that field is required and you'll have to later include it in the JS validation below, otherwise skip that piece of code-->
	<!-- After validation, there will be a red star next to First Name indicating the the field is required-->
	
	
	
	
	
	<div class="form_row">
        		<div class="label">
         	   		<label for="sf_field_drop4_2"><strong>Please include additional information below:</strong></label>                  <!-- <strong> field is just there to make the title bold-->
				</div>
        		<div class="textarea">
          			<textarea type="text" name="sf_field_drop4_2" id="sf_field_drop4_2" autocomplete="OFF" autofocus=""></textarea>      <!-- typical way to go around textarea box, kinda like previos one, but wider -->
    			</div>
			</div>
    	</div>   <!-- here I made a mistake on purpose, number 44 is red, means something is wrong, navigate mouse on it and it'll tell you. In this case I skipped a closing div tag-->   
				<!-- ONE exception to this, ignore red at the very beginning of the page, it looks for Doctype but you don't need it for a form-->
	
	
	
	
	
	<div class="form_row">
        <div class="label">
            <label for="Email">Email Address:<span class="su_required" title="This is a required field">*</span></label>   <!-- typical way to go around email address-->
		</div>
        <div class="input">
            <input type="email" id="Email" name="Email" required="">
        </div>
    </div>
	
	
	
	
	
	
	
	<div class="form_row">
		<div class="label">
			<label for="State">U.S. State/Canada Province:</label>
		</div>
		<div class="select">
        	<select name="State" id="State">
			<option selected="true" value=""> - Select your state/province - </option>                            <!-- typical way to go around Select boxes-->
            <option value="AL">ALABAMA</option>
            <option value="AK">ALASKA </option>
            <option value="AS">AMERICAN SAMOA </option>
            <option value="AZ">ARIZONA </option>
			</select>
		</div>
	</div>
	
	
	
	
	
	
	<div class="form_row"><label>Are you an international student?</label>   <!--label field here might not be needed, depending on the page-->
    
    		<div class="input_radio">
    			<label for="Yes">
    				<input name="Yes_No" autocomplete="OFF" id="Yes3" type="radio" value="Yes" />Yes</label>             <!-- typical way to go around Radio buttons-->
    		</div>
			
			<div class="input_radio">
    			<label for="No">
    				<input name="Yes_No" autocomplete="OFF" id="No3" type="radio" value="No" />No</label>
    		</div>
		</div>
	
	
	
	
	
	
	
	
	<div class="form_row">
    
    		<div class="input_checkbox">
    			<label for="Fall">
    				<input name="Semester" autocomplete="OFF" id="Fall" type="checkbox" value="Fall" />Fall</label>       <!-- typical way to go around Checkbox buttons-->
    		</div>
			
			<div class="input_checkbox">
    			<label for="Spring">
    				<input name="Semester" autocomplete="OFF" id="Spring" type="checkbox" value="Spring" />Spring</label>
    		</div>
		
		</div>
	
	
</fieldset>    <!-- Every tag you open has to close with one exception (Ask me about it), you can make multiple fieldset tags throughout the page, use your own judgement, you might want to separate different sections or just keep it one giant fieldset-->
	





<!-- starting from line 130, the validation part begins-->
	
<fieldset>         
        <div>
		 	<input type="text" name="recaptcha-su_fix" id="recaptcha-su_fix" style="visibility: hidden;" />    <!-- lines 130-138 you keep the same for all pages -->
         	<div class="g-recaptcha" data-sitekey="6Lf_71oUAAAAAEa2DgPy0P_TKJQVBRV3LX1nMZNO"/>
		</div>
		<div class="form_row"> 
        	<input name="btnSubmit" id="btnSubmit" type="submit" value="Submit">
        </div>
</fieldset>


	<link rel="stylesheet" media="screen" href="https://www.suffolk.edu/su_apps/styles/validate.min.css" />
    <script type="text/javascript" src="https://www.suffolk.edu/su_apps/scripts/validate.min.js"></script>
	<script src="https://www.google.com/recaptcha/api.js"></script>

  <script type="text/javascript">
  (function() {
    var formName = "third_form"; 														/* form name can be different for each page, check with HTML at the beginning of the form*/
    var formAction = "https://portalpro.suffolk.edu/webas/FormToEmail";
    var formreCaptcha = document.getElementById("recaptcha-su_fix");
    var formSettings = [{
        name: 'FirstName',                                                        /*name field is what the JS will look for to validate, make sure you give each field a different name too*/
        display: 'First Name',													/*display field is what the user will see if he/she skips the required field, form won't submit unless the required field has been filled*/
        rules: 'required'
    },{
        name: 'Email',
		display: 'Email Address',                
        rules: 'valid_email|required'                                       /* Email required field looks slighly diferent, use this rules line for all email fields*/    
    }, {
        name: "recaptcha-su_fix",											
        display: "I'm Not a Robot",											/*lines 159 to 181 are also required for all forms*/
        rules: 'required',
        depends: function() {

            var response = grecaptcha.getResponse();
            if (response.length === 0) {
                formreCaptcha.value = "";
                return true;
            } else {
                formreCaptcha.value = "validated";
                return false;
            }

        }
    }];
    window.su_global.formAction = formAction;
    window.su_global.validateLogic(formName, formSettings);
})();
	</script>
</form>	    

<script type="text/javascript">forms1nameString(document.main_form.elements["form:names"]);</script>	
