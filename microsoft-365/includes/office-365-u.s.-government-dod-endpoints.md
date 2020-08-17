<!--THIS FILE IS AUTOMATICALLY GENERATED. MANUAL CHANGES WILL BE OVERWRITTEN.-->
<!--Please contact the Office 365 Endpoints team with any questions.-->
<!--USGovDoD endpoints version 2020072800-->
<!--File generated 2020-08-08 08:00:08.2943-->

## <a name="exchange-online"></a>Exchange Online

-ID | Categorie | AP | Hostadressen | Haven
-- | -------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------
1 | Ideaal<BR>Vereist | Ja | `outlook-dod.office365.us, webmail.apps.mil`<BR>`40.66.24.0/21, 131.253.80.0/24, 131.253.83.64/26, 131.253.84.0/26, 131.253.84.128/26, 131.253.87.0/25, 131.253.87.128/28, 131.253.87.160/27, 131.253.87.192/28, 131.253.87.224/28, 131.253.88.16/28, 131.253.88.64/28, 131.253.88.80/28, 131.253.88.112/28, 131.253.88.176/28, 131.253.88.208/28, 131.253.88.224/28, 2001:489a:2200:500::/56` | **TCP:** 443, 80
3 | Standaard<BR>Vereist | Ja | `outlook-dod.office365.us, webmail.apps.mil` | **TCP:** 143, 25, 587, 993, 995
vijf | Standaard<BR>Vereist | Ja | `attachments-dod.office365-net.us, autodiscover.<tenant>.mail.onmicrosoft.com, autodiscover.<tenant>.mail.onmicrosoft.us, autodiscover.<tenant>.onmicrosoft.com, autodiscover.<tenant>.onmicrosoft.us, autodiscover-s-dod.office365.us` | **TCP:** 443, 80
zes | Gelijktijdige<BR>Vereist | Ja | `*.protection.apps.mil, *.protection.office365.us`<BR>`23.103.191.0/24, 23.103.199.0/25, 23.103.204.0/22, 52.181.167.52/32, 52.181.167.91/32, 52.182.95.219/32, 2001:489a:2202::/62, 2001:489a:2202:8::/62, 2001:489a:2202:2000::/63` | **TCP:** 25 mei 443

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online en OneDrive voor bedrijven

-ID | Categorie | AP | Hostadressen | Haven
-- | -------------------- | --- | ------------------------------------------------------------------------------------------------------------------- | ----------------
aanhaling | Ideaal<BR>Vereist | Ja | `*.dps.mil, *.sharepoint-mil.us`<BR>`20.34.12.0/22, 104.212.48.0/23, 2001:489a:2204::/63, 2001:489a:2204:c00::/54` | **TCP:** 443, 80
10 | Standaard<BR>Vereist | Nee | `*.wns.windows.com, g.live.com, odc.officeapps.live.com, officeclient.microsoft.com, oneclient.sfx.ms` | **TCP:** 443, 80
19 | Gelijktijdige<BR>Vereist | Ja | `*.od.apps.mil, od.apps.mil` | **TCP:** 443, 80
Maxi | Standaard<BR>Vereist | Nee | `*.svc.ms, az741266.vo.msecnd.net, pf.pipe.aria.microsoft.com, spoprod-a.akamaihd.net, static.sharepointonline.com` | **TCP:** 443, 80

## <a name="skype-for-business-online-and-microsoft-teams"></a>Skype voor bedrijven online en Microsoft teams

-ID | Categorie | AP | Hostadressen | Haven
-- | -------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -----------------------------------------------
7,5 | Ideaal<BR>Vereist | Ja | `*.dod.teams.microsoft.us, *.online.dod.skypeforbusiness.us, dod.teams.microsoft.us`<BR>`52.127.64.0/21, 52.180.249.148/32, 52.180.252.118/32, 52.180.252.187/32, 52.180.253.137/32, 52.180.253.154/32, 52.181.165.243/32, 52.181.166.119/32, 52.181.167.43/32, 52.181.167.64/32, 52.181.200.104/32, 104.212.32.0/22, 104.212.60.0/23, 195.134.240.0/22` | **TCP:** 443<BR>**UDP:** 3478, 3479, 3480, 3481
22 | Standaard<BR>Vereist | Nee | `dodteamsapuiwebcontent.blob.core.usgovcloudapi.net, msteamsstatics.blob.core.usgovcloudapi.net, statics.teams.microsoft.com` | **TCP:** 443
centimeter | Gelijktijdige<BR>Vereist | Ja | `endpoint1-proddodcecompsvc-dodc.streaming.media.usgovcloudapi.net, endpoint1-proddodeacompsvc-dode.streaming.media.usgovcloudapi.net`<BR>`52.181.180.135/32, 52.182.53.6/32` | **TCP:** 443

## <a name="microsoft-365-common-and-office-online"></a>Microsoft 365 common en Office Online

-ID | Categorie | AP | Hostadressen | Haven
-- | ------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------
23:00 | Gelijktijdige<BR>Vereist | Ja | `*.dod.online.office365.us`<BR>`52.127.80.0/23, 52.181.164.39/32, 52.182.95.191/32` | **TCP:** 443
12 | Standaard<BR>Vereist | Ja | `*.dod.cdn.office365.us`<BR>`52.181.164.39/32, 52.182.95.191/32` | **TCP:** 443
dertien | Gelijktijdige<BR>Vereist | Ja | `*.gov.us.microsoftonline.com, adminwebservice.gov.us.microsoftonline.com, becws.gov.us.microsoftonline.com, dod-graph.microsoft.us, graph.microsoftazure.us, login.microsoftonline.us, provisioningapi.gov.us.microsoftonline.com`<BR>`20.140.232.0/23, 52.126.194.0/23` | **TCP:** 443
14 | Standaard<BR>Vereist | Nee | `*.msauth.net, *.msauthimages.us, *.msftauth.net, *.msftauthimages.us, clientconfig.microsoftonline-p.net, graph.windows.net, login.microsoftonline.com, login.microsoftonline-p.com, login.windows.net, loginex.microsoftonline.com, login-us.microsoftonline.com, mscrl.microsoft.com, nexus.microsoftonline-p.com, secure.aadcdn.microsoftonline-p.com` | **TCP:** 443
15 | Gelijktijdige<BR>Vereist | Ja | `portal.apps.mil, webshell.dodsuite.office365.us, www.ohome.apps.mil`<BR>`52.180.251.166/32, 52.181.160.19/32, 52.181.160.113/32, 52.181.160.236/32, 52.182.54.237/32, 52.182.92.132/32` | **TCP:** 443
zestien | Gelijktijdige<BR>Vereist | Ja | `*.osi.apps.mil, dod.loki.office365.us`<BR>`52.127.72.0/21, 2001:489a:2206::/48` | **TCP:** 443
19 | Standaard<BR>Vereist | Nee | `activation.sls.microsoft.com, crl.microsoft.com, go.microsoft.com, insertmedia.bing.office.net, ocsa.officeapps.live.com, ocsredir.officeapps.live.com, ocws.officeapps.live.com, office15client.microsoft.com, officecdn.microsoft.com, officecdn.microsoft.com.edgesuite.net, officepreviewredir.microsoft.com, officeredir.microsoft.com, ols.officeapps.live.com, r.office.microsoft.com` | **TCP:** 443, 80
Mini | Standaard<BR>Vereist | Nee | `cdn.odc.officeapps.live.com, odc.officeapps.live.com, officeclient.microsoft.com` | **TCP:** 443, 80
records | Standaard<BR>Vereist | Nee | `lpcres.delve.office.com` | **TCP:** 443
25 | Standaard<BR>Vereist | Nee | `*.cdn.office.net` | **TCP:** 443
27 | Gelijktijdige<BR>Vereist | Ja | `*.compliance.apps.mil, *.security.apps.mil, compliance.apps.mil, security.apps.mil`<BR>`23.103.191.0/24, 23.103.199.0/25, 23.103.204.0/22, 52.181.167.52/32, 52.181.167.91/32, 52.182.95.219/32, 2001:489a:2202::/62, 2001:489a:2202:8::/62, 2001:489a:2202:2000::/63` | **TCP:** 443, 80
27.08.2002 | Gelijktijdige<BR>Vereist | Ja | `*.dod.microsoftstream.us, *.media.osi.apps.mil`<BR>`20.140.163.0/24, 20.140.164.0/24` | **TCP:** 1935, 1936, 2935, 2936, 443