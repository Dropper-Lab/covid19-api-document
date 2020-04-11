[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![HitCount](http://hits.dwyl.io/Dropper-Lab/covid19-api-document.svg)](http://hits.dwyl.io/Dropper-Lab/covid19-api-document)
![GitHub last commit](https://img.shields.io/github/last-commit/Dropper-Lab/covid19-api-document.svg)

[Korean](./README-ko_KR.md) | [English](./README-en_EN.md)

# covid19-api-document
The API document for COVID19 API from Dropper Lab.

## Contents Table

- [I. Authentication](#I)
    - [Value properties for authentication](#I-1)
- [II. Korean local patient count](#II)
    - [Value properties for request](#II-1)
    - [Support area](#II-2)
    - [Return field](#II-3)
    - [Return example](#II-4)
- [III. International patient count](#III)
    - [Value properties for request](#III-1)
    - [Support area](#III-2)
    - [Return field](#III-3)
    - [Return example](#III-4)

<div name='I'/>

## I. Authentication

All the APIs we provide are available in the HTTPS-based REST API.

Any platform or application developed in any language can be requested and used, and APIKey data is provided by the HTTP header for user authentication.

<div name='I-1'/>

### Value properties for authentication

|method|attribute|data type|essential|detail|
|:-:|:-:|:-:|:-:|:-:|
|HTTP Header|APIKey|string|Yes|Unique key for user identification|

<div name='II'/>

## II. Korean local patient count

**API address** : **`GET`** https://api.dropper.tech/covid19/status/korea

**API detail** : Provides the number of COVID19 patients in Korea.

<div name='II-1'/>

### Value properties for request

|attribute|data type|essential|detail|
|:-:|:-:|:-:|:-:|
|locale|string|Yes|City name|

<div name='II-2'/>

### Support area

|value|detail|
|:-:|:-:|
|synthesize|The whole region|
|busan|Busan Metropolitan City|
|chungbuk|Chungcheongbuk-do Province|
|chungnam|Chungcheongnam-do Province|
|daegu|Daegu Metropolitan City|
|daejeon|Daejeon Metropolitan City|
|gangwon|Gangwon Metropolitan City|
|gwangju|Gwangju Metropolitan City|
|gyeongbuk|Gyeongsangbuk-do Province|
|gyeonggi|Gyeonggi-do Province|
|gyeongnam|Gyeongsangnam-do Province|
|incheon|Incheon Metropolitan City|
|jeju|Jeju Special Self-Governing Island|
|jeonbuk|Jeollabuk-do Province|
|jeonnam|Jeollanam-do Province|
|sejong|Sejong Special Self-Governing City|
|seoul|Seoul Metropolitan City|
|ulsan|Ulsan Metropolitan City|
|quarantine|Quarantine Station|

<div name='II-3'/>

### Return field

|attribute|data type|detail|
|:-:|:-:|:-:|
|timestamp|int|When the data was collected|
|announced_timestamp|int|When the data was released|
|increased|int|Number of increased patients|
|increased_foreign|int|Number of increased patients brought in from abroad|
|increased_local|int|Number of increased locally infected patients|
|certified|int|Number of confirmed patients|
|isolated|int|Number of isolated patients|
|deisolated|int|Number of unisolated patients|
|dead|int|Number of dead patients|
|percentage|float|Infection rate|

<div name='II-4'/>

### Return example

```json
{
   "status": {
      "code": 200,
      "message": "Successfully loaded 1 rows."
   },
   "data": [
      {
         "timestamp": 1586616409,
         "announced_timestamp": 1586530800,
         "increased": 30,
         "certified": 10480,
         "deisolated": 7243,
         "dead": 211,
         "percentage": 20.21
      }
   ]
}
```

```json
{
   "status": {
      "code": 200,
      "message": "Successfully loaded 1 rows."
   },
   "data": [
      {
         "timestamp": 1586616409,
         "announced_timestamp": 1586530800,
         "increased": 4,
         "certified": 599,
         "deisolated": 195,
         "dead": 2,
         "percentage": 6.15
      }
   ]
}
```

<div name='II'/>

## III. International patient count

**API address** : **`GET`** https://api.dropper.tech/covid19/status/global

**API detail** : Provides the number of international COVID19 patients.

<div name='III-1'/>

### Value properties for request

|attribute|data type|essential|detail|
|:-:|:-:|:-:|:-:|
|locale|string|Yes|Country name|

<div name='III-2'/>

### supported country

|value|detail|
|:-:|:-:|
|saintpierreandmiquelon|Saint Pierre and Miquelon|
|synthesize|The whole region|
|falklandislands|Falkland Islands|
|caribbeannetherlands|Caribbean Netherlands|
|northernmarianaislands|Northern Mariana Islands|
|britishvirginislands|British Virgin Islands|
|angula|Angula|
|turksandcaicosislands|Turks and Caicos Islands|
|isleofman|Isle of Man|
|greenland|Greenland|
|newcaledonia|New Caledonia|
|montserrat|Montserrat|
|sintmaartin|Sint Maarten|
|bermuda|Bermuda|
|aruba|Aruba|
|unitedstatesvirginislands|United States Virgin Islands|
|guam|Guam|
|puertorico|Puerto Rico|
|mayotte|Mayotte|
|curacao|Curacao|
|cayman|Cayman Islands|
|guadeloupe|Guadeloupe|
|regionreunion|Region Reunion|
|jersey|Jersey Island|
|polynesia|Polynesia|
|guernsey|Guernsey Island|
|faroeislands|Faroe Islands|
|guyane|Guyane|
|martinique|Martinique|
|vatican|Vatican|
|saintbarthelemy|Saint Barthelemy|
|saintmartin|Saint Martin|
|gibraltar|Gibraltar|
|palestine|Palestine|
|japan_cruise|Japanese Cruise|
|sainttomeprincipe|Saint Tome Principe|
|southsudan|South Sudan|
|sierraleone|Sierra Leone|
|burundi|Burundi|
|botswana|Botswana|
|marley|Marley|
|guineabissau|Guinea Bissau|
|mozambique|Mozambique|
|uganda|Uganda|
|eritrea|Eritrea|
|angola|Angola|
|madagascar|Madagascar|
|zimbabwe|Zimbabwe|
|capeverde|Capeverde|
|somalia|Somalia|
|niger|Niger|
|chad|Chad|
|zambia|Zambia|
|gambia|Gambia|
|mauritius|Mauritius|
|djibouti|Djibouti|
|tanzania|tanzania|
|liberia|Liberia|
|benin|Benin|
|seychelles|Seychelles|
|rwanda|Rwanda|
|mauritania|Mauritania|
|eswatini|Eswatini|
|guinea|Guinea|
|congo|Congo|
|centralafricanrepublic|Central African Republic|
|namibia|Namibia|
|kenya|Kenya|
|guineaecuatorial|Guinea Ecuatorial|
|ghana|Ghana|
|gabon|Gabon|
|ethiopia|Ethiopia|
|sudan|Sudan|
|ivorycoast|Ivory Coast|
|drcongo|DR Congo|
|burkinafaso|Burkina Faso|
|republiquetogolaise|République Togolaise|
|republicofsouthafrica|Republic of South Africa|
|cameroon|Cameroon|
|senegal|Senegal|
|nigeria|Nigeria|
|papuanewguinea|Papua New Guinea|
|fiji|Fiji|
|newzealand|New Zealand|
|australia|Australia|
|kosovo|Kosovo|
|montenegro|Montenegro|
|turkey|Turkey|
|cyprus|Cyprus|
|albania|Albania|
|moldova|Moldova|
|malta|Malta|
|bulgaria|Bulgaria|
|slovakia|Slovakia|
|serbia|Serbia|
|liechtenstein|Liechtenstein|
|slovenija|Slovenija|
|bosnaihercegovina|Bosna Hercegovina|
|hungary|Hungary|
|ukraine|Ukraine|
|poland|Poland|
|andora|Andora|
|latvia|Latvia|
|portugal|Portugal|
|czecho|Czecho|
|ireland|Ireland|
|armenia|Armenia|
|luxembourg|Luxembourg|
|monaco|Monaco|
|iceland|Iceland|
|azerbaijan|Azerbaijan|
|sanmarino|San Marino|
|lithuania|Lithuania|
|belarus|Belarus|
|nederlands|Nederlands|
|romania|Romania|
|norway|Norway|
|macedonia|Macedonia|
|greece|Greece|
|georgia|Georgia|
|eesti|Eesti|
|danmark|Danmark|
|belgium|Belgium|
|swiss|Swiss|
|sweden|Sweden|
|finland|Finland|
|croatia|Croatia|
|austria|Austria|
|spain|Spain|
|england|England|
|france|France|
|germany|Germany|
|italiana|Italiana|
|saintkittsandnevis|Saint Kitts and Nevis|
|dominicanfederation|Dominican Federation|
|belize|Belize|
|grenada|Grenada|
|haiti|Haiti|
|nicaragua|Nicaragua|
|barbados|Barbados|
|elsalvador|El Salvador|
|bahamas|Bahamas|
|guatemala|Guatemala|
|suriname|Suriname|
|saintlucia|Saint Lucia|
|uruguay|Uruguay|
|trinidadandtobago|Trinidad and Tobago|
|antiguaandbarbuda|Antigua and Barbuda|
|venezuela|Venezuela|
|guyana|Guyana|
|cuba|Cuba|
|stvincentandthegrenadines|Saint Vincent and the Grenadines|
|honduras|Honduras|
|jamaica|Jamaica|
|bolivia|Bolivia|
|panama|Panama|
|paraguay|Paraguay|
|costarica|Costa Rica|
|peru|Peru|
|columbia|Columbia|
|chile|Chile|
|argentina|Argentina|
|dominican|Dominican|
|ecuador|Ecuador|
|mexico|Mexico|
|brasil|Brasil|
|canada|Canada|
|usa|USA|
|libya|Libya|
|syria|Syria|
|morocco|Morocco|
|saudiarabia|Saudi Arabia|
|tunisia|Tunisia|
|jordan|Jordan|
|qatar|Qatar|
|algeria|Algeria|
|egypt|Egypt|
|israel|Israel|
|lebanon|Lebanon|
|oman|Oman|
|iraq|Iraq|
|uae|UAE|
|bahrain|Bahrain|
|kuwait|Kuwait|
|iran|Iran|
|laos|Laos|
|myanmar|Myanmar|
|easttimor|East Timor|
|kyrgyzstan|Kyrgyzstan|
|uzbekistan|Uzbekistan|
|kazakhstan|Kazakhstan|
|mongolia|Mongolia|
|brunei|Brunei|
|bangladesh|Bangladesh|
|maldives|Maldives|
|bhutan|Bhutan|
|indonesia|Indonesia|
|pakistan|Pakistan|
|afghanistan|Afghanistan|
|srilanka|Srilanka|
|russia|Russia|
|nepal|Nepal|
|cambodia|Cambodia|
|philippines|Philippines|
|india|India|
|vietnam|Vietnam|
|malaysia|Malaysia|
|thailand|Thailand|
|singapura|Singapura|
|japan|Japan|
|macau|Macau|
|taiwan|Taiwan|
|hongkong|Hongkong|
|china|China|

<div name='III-3'/>

### Return field

|attribute|data type|detail|
|:-:|:-:|:-:|
|timestamp|int|When the data was collected|
|increased|int|Number of increased patients|
|certified|int|Number of confirmed patients|
|dead|int|Number of dead patients|

<div name='III-4'/>

### Return example

```json
{
    "status": {
        "code": 200,
        "message": "Successfully loaded 1 rows."
    },
    "data": [
        {
            "announced_timestamp": 1015632000,
            "timestamp": 1583766004,
            "certified": 57,
            "dead": 0
        }
    ]
}
```

```json
{
    "status": {
        "code": 200,
        "message": "Successfully loaded 1 rows."
    },
    "data": [
        {
            "announced_timestamp": 1015632000,
            "timestamp": 1583766004,
            "certified": 80735,
            "dead": 3119
        }
    ]
}
```