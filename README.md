# MIS581
Portfoilo Project
****SAS CODE***
****MIGRAINE CLASSIFICATION CODES*****
/* Generated Code (IMPORT) */
/* Source File: Migraine Classification.csv */
/* Source Path: /home/u60628596/MIS581 */
/* Code generated on: 7/12/23, 9:18 AM */

%if %sysfunc(exist(WORK.'MIGRAINE CLASSIFICATION'n)) %then %do;
proc sql;
    drop table WORK.'MIGRAINE CLASSIFICATION'n;
run;
%end;


FILENAME REFFILE '/home/u60628596/MIS581/Migraine Classification.csv';

PROC IMPORT DATAFILE=REFFILE
	DBMS=CSV
	OUT=WORK.'MIGRAINE CLASSIFICATION'n;
	GETNAMES=YES;
RUN;

PROC CONTENTS DATA=WORK.'MIGRAINE CLASSIFICATION'n; RUN;


%web_open_table(WORK.'MIGRAINE CLASSIFICATION'n);

****SUMMARY STAT*****
/*
 *
 * Task code generated by SAS Studio 3.8 
 *
 * Generated on '7/12/23, 9:28 AM' 
 * Generated by 'u60628596' 
 * Generated on server 'ODAWS01-USW2.ODA.SAS.COM' 
 * Generated on SAS platform 'Linux LIN X64 3.10.0-1062.9.1.el7.x86_64' 
 * Generated on SAS version '9.04.01M7P08062020' 
 * Generated on browser 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0' 
 * Generated on web client 'https://odamid-usw2.oda.sas.com/SASStudio/main?locale=en_US&zone=GMT-06%253A00&ticket=ST-52902-zAvoC9yJQ1V4yhdYdeU7-cas' 
 *
 */

ods noproctitle;
ods graphics / imagemap=on;

proc means data=WORK.'MIGRAINE CLASSIFICATION'n chartype mean std min max n 
		vardef=df;
	var Age Duration Frequency Location Character Intensity Nausea Vomit 
		Phonophobia Photophobia Visual Sensory Dysphasia Dysarthria Vertigo Tinnitus 
		Hypoacusis Diplopia Defect Ataxia Conscience Paresthesia DPF;
run;


****CORRELATION ANALYSIS*******
/*
 *
 * Task code generated by SAS Studio 3.8 
 *
 * Generated on '7/12/23, 9:35 AM' 
 * Generated by 'u60628596' 
 * Generated on server 'ODAWS01-USW2.ODA.SAS.COM' 
 * Generated on SAS platform 'Linux LIN X64 3.10.0-1062.9.1.el7.x86_64' 
 * Generated on SAS version '9.04.01M7P08062020' 
 * Generated on browser 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0' 
 * Generated on web client 'https://odamid-usw2.oda.sas.com/SASStudio/main?locale=en_US&zone=GMT-06%253A00&ticket=ST-52902-zAvoC9yJQ1V4yhdYdeU7-cas' 
 *
 */

ods noproctitle;
ods graphics / imagemap=on;

proc corr data=WORK.'MIGRAINE CLASSIFICATION'n pearson nosimple plots=none;
	var Duration;
	with Age Frequency Location Character Intensity Nausea Vomit Phonophobia 
		Photophobia Visual Sensory Dysphasia Dysarthria Vertigo Tinnitus Hypoacusis 
		Diplopia Defect Ataxia Conscience Paresthesia DPF;
run;

*****TREATMENT OF MIGRANIE HEADACHES*******
/* Generated Code (IMPORT) */
/* Source File: Treatment of Mirgraine Heasaches.csv */
/* Source Path: /home/u60628596/MIS581 */
/* Code generated on: 7/12/23, 9:26 AM */

%if %sysfunc(exist(WORK.'TREATMENT OF MIGRAINE HEADACHES'n)) %then %do;
proc sql;
    drop table WORK.'TREATMENT OF MIGRAINE HEADACHES'n;
run;
%end;


FILENAME REFFILE '/home/u60628596/MIS581/Treatment of Mirgraine Heasaches.csv';

PROC IMPORT DATAFILE=REFFILE
	DBMS=CSV
	OUT=WORK.'TREATMENT OF MIGRAINE HEADACHES'n;
	GETNAMES=YES;
RUN;

PROC CONTENTS DATA=WORK.'TREATMENT OF MIGRAINE HEADACHES'n; RUN;


%web_open_table(WORK.'TREATMENT OF MIGRAINE HEADACHES'n);

******SUMMARY STAT*****
/*
 *
 * Task code generated by SAS Studio 3.8 
 *
 * Generated on '7/12/23, 9:32 AM' 
 * Generated by 'u60628596' 
 * Generated on server 'ODAWS01-USW2.ODA.SAS.COM' 
 * Generated on SAS platform 'Linux LIN X64 3.10.0-1062.9.1.el7.x86_64' 
 * Generated on SAS version '9.04.01M7P08062020' 
 * Generated on browser 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0' 
 * Generated on web client 'https://odamid-usw2.oda.sas.com/SASStudio/main?locale=en_US&zone=GMT-06%253A00&ticket=ST-52902-zAvoC9yJQ1V4yhdYdeU7-cas' 
 *
 */

ods noproctitle;
ods graphics / imagemap=on;

proc means data=WORK.'TREATMENT OF MIGRAINE HEADACHES'n chartype mean std min 
		max n vardef=df;
	var VAR1 id time dos age airq;
run;

********CORRELATION ANALYSIS*****
/*
 *
 * Task code generated by SAS Studio 3.8 
 *
 * Generated on '7/12/23, 9:38 AM' 
 * Generated by 'u60628596' 
 * Generated on server 'ODAWS01-USW2.ODA.SAS.COM' 
 * Generated on SAS platform 'Linux LIN X64 3.10.0-1062.9.1.el7.x86_64' 
 * Generated on SAS version '9.04.01M7P08062020' 
 * Generated on browser 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0' 
 * Generated on web client 'https://odamid-usw2.oda.sas.com/SASStudio/main?locale=en_US&zone=GMT-06%253A00&ticket=ST-52902-zAvoC9yJQ1V4yhdYdeU7-cas' 
 *
 */

ods noproctitle;
ods graphics / imagemap=on;

proc corr data=WORK.'TREATMENT OF MIGRAINE HEADACHES'n pearson nosimple 
		plots=none;
	var dos;
	with VAR1 id time age airq;
run;

******LINEAR REGRESSION******
/*
 *
 * Task code generated by SAS Studio 3.8 
 *
 * Generated on '7/12/23, 9:42 AM' 
 * Generated by 'u60628596' 
 * Generated on server 'ODAWS01-USW2.ODA.SAS.COM' 
 * Generated on SAS platform 'Linux LIN X64 3.10.0-1062.9.1.el7.x86_64' 
 * Generated on SAS version '9.04.01M7P08062020' 
 * Generated on browser 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0' 
 * Generated on web client 'https://odamid-usw2.oda.sas.com/SASStudio/main?locale=en_US&zone=GMT-06%253A00&ticket=ST-52902-zAvoC9yJQ1V4yhdYdeU7-cas' 
 *
 */

ods noproctitle;
ods graphics / imagemap=on;

proc reg data=WORK.'TREATMENT OF MIGRAINE HEADACHES'n alpha=0.05 
		plots(only)=(diagnostics residuals fitplot observedbypredicted);
	model dos=airq /;
	run;
quit;
