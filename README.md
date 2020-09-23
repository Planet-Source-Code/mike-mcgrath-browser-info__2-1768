<div align="center">

## Browser Info


</div>

### Description

Thsi code shows how to gather browser info using Javascript. It gathers the date, time, browser type, browser version number, whether it is java enabled, the platform the user is running and the user's screen resolution.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mike McGrath](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mike-mcgrath.md)
**Level**          |Intermediate
**User Rating**    |5.0 (25 globes from 5 users)
**Compatibility**  |
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__2-68.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mike-mcgrath-browser-info__2-1768/archive/master.zip)





### Source Code

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN">
<HTML>
<HEAD>
<TITLE>Browser Info</TITLE>
<!-- THREE STEPS TO INSTALL BROWSER INFO:
 1. Copy the coding into the HEAD of your HTML document
 2. Copy the coding into the BODY TAG of your document
 3. Put the last coding into the BODY of your HTML document -->
<!-- STEP ONE: Paste this code into the HEAD of your HTML document -->
<SCRIPT LANGUAGE="javascript">
<!-- Original: Mike McGrath (mike_mcgrath@lineone.net) -->
<!-- Web Site: http://website.lineone.net/~mike_mcgrath/index.htm -->
<!-- BEGIN --
function GoDate()
{
 TDay = new Array("Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday");
 TMonth= new Array("January","February","March","April","May","June","July","August","September","October","November","December");
 TDate = new Date();
 CurYear = TDate.getYear();
 CurYear=(CurYear<2000)?1900+CurYear:CurYear;
 CurMonth = TDate.getMonth();
 CurDayOw = TDate.getDay();
 CurDay  = TDate.getDate();
 TheDate = TDay[CurDayOw] + ', ';
 TheDate += TMonth[CurMonth] + ' ';
 TheDate += CurDay + ', ';
 TheDate += CurYear;
 document.f.date_box.value = TheDate;
}
function GoClock24()
{
 TTime = new Date();
 CurHour = TTime.getHours();
 CurMin = TTime.getMinutes();
 CurSec = TTime.getSeconds();
 TheTime = CurHour;// Add them
 TheTime += ((CurMin < 10) ? ':0' : ':') + CurMin;
 TheTime += ((CurSec < 10) ? ':0' : ':') + CurSec;
 document.f.time_box.value = TheTime;
 window.setTimeout('GoClock24()',1000);
}
function GoBrowser(form)
{
 form.browser_box.value=navigator.appName;
 form.version_box.value= navigator.appVersion;
 if (navigator.javaEnabled()) var JavaStatus="Java Enabled";
 else
	var JavaStatus="Java Not Present/Enabled";
 form.javastatus_box.value=JavaStatus;
 var OpSys="Other";
 if(navigator.userAgent.indexOf('Win')!=-1)
 {
  if (navigator.userAgent.indexOf('95')!=-1)OpSys="Windows95";
  else if(navigator.userAgent.indexOf('98')!=-1)OpSys="Windows95";
  else if(navigator.userAgent.indexOf('Win')!=-1)OpSys="Windows3.1 or NT";
 }
 else if(navigator.userAgent.indexOf('Mac') != -1)OpSys="Macintosh";
 form.opsys_box.value=OpSys;
 form.res_box.value=window.screen.width+" X "+window.screen.height;
}
//-- END -->
</SCRIPT>
</HEAD>
<!-- STEP TWO: Paste this code into the BODY TAG of your HTML document -->
<BODY BGCOLOR="brown" onLoad="GoBrowser(this.document.f); GoDate(); GoClock24();">
<!-- STEP THREE: Paste this code into the BODY of your HTML document -->
<CENTER>
<FORM NAME="f">
 <TABLE BORDER=1 BGCOLOR=#C0C0C0>
 <TH COLSPAN=2 ALIGN=CENTER>Browser Info</TH>
 <TR>
  <TD><SMALL>Date : </SMALL></TD>
  <TD><INPUT NAME="date_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Time : </SMALL></TD>
  <TD><INPUT NAME="time_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Browser : </SMALL></TD>
  <TD><INPUT NAME="browser_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Version : </SMALL></TD>
  <TD><INPUT NAME="version_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Java : </SMALL></TD>
  <TD><INPUT NAME="javastatus_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Platform : </SMALL></TD>
  <TD><INPUT NAME="opsys_box" SIZE=40></TD></TR>
 <TR>
  <TD><SMALL>Resolution : </SMALL></TD>
  <TD><INPUT NAME="res_box" SIZE=40></TD>
 </TR>
 </TABLE>
</FORM>
</CENTER>
</BODY>
</HTML>
```

