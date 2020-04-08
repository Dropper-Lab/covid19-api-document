[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![HitCount](http://hits.dwyl.io/Dropper-Lab/covid19-api-document.svg)](http://hits.dwyl.io/Dropper-Lab/covid19-api-document)
![GitHub last commit](https://img.shields.io/github/last-commit/Dropper-Lab/covid19-api-document.svg)

[Korean](./README-ko_KR.md) | [English](./README-en_EN.md)

# covid19-api-document
Dropper Lab.의 COVID19 API를 위한 공식 도큐먼트

## Contents Table

- [I. 인증](#I)
    - [인증을 위한 값 속성](#I-1)
- [II. 국내 환자수](#II)
    - [요청 값 속성](#II-1)
    - [지원 지역](#II-2)
    - [반환 필드](#II-3)
    - [반환 예시](#II-4)
- [III. 국외 환자수](#III)
    - [요청 값 속성](#III-1)
    - [지원 지역](#III-2)
    - [반환 필드](#III-3)
    - [반환 예시](#III-4)

<div name='I'/>

## I. 인증

저희 Dropper가 제공하는 모든 API는 HTTPS 기반인 REST API로 제공됩니다.

어떤 언어로 개발한 플랫폼 또는 애플리케이션이던 상관없이 요청하여 사용이 가능하며, 사용자의 인증을 위해 HTTP 헤더로 APIKey 데이터를 제공 받습니다.

<div name='I-1'/>

### 인증을 위한 값 속성

|전달방식|속성|자료형|필수|설명|
|:-:|:-:|:-:|:-:|:-:|
|HTTP Header|APIKey|string|Yes|사용자 식별을 위한 고유 키|

<div name='II'/>

## II. 국내 환자수

**API 주소** : **`GET`** https://api.dropper.tech/covid19/status/korea

**API 설명** : 한국의 COVID19 환자수를 제공합니다.

<div name='II-1'/>

### 요청 값 속성

|속성|자료형|필수|설명|
|:-:|:-:|:-:|:-:|
|locale|string|Yes|조회하고자 하는 도시명|

<div name='II-2'/>

### 지원 지역

|값|설명|
|:-:|:-:|
|synthesize|지역 전체|
|busan|부산|
|chungbuk|충북|
|chungnam|충남|
|daegu|대구|
|daejeon|대전|
|gangwon|강원|
|gwangju|강주|
|gyeongbuk|경북|
|gyeonggi|경기|
|gyeongnam|경남|
|incheon|인천|
|jeju|제주|
|jeonbuk|전북|
|jeonnam|전남|
|sejong|세종|
|seoul|서울|
|ulsan|울산|
|quarantine|검역|

<div name='II-3'/>

### 반환 필드

|속성|자료형|설명|
|:-:|:-:|:-:|
|timestamp|int|데이터를 수집한 시점|
|announced_timestamp|int|데이터가 발표된 시점|
|increased|int|늘어난 환자의 수|
|certified|int|확진된 환자의 수|
|deisolated|int|격리해제된 환자의 수|
|dead|int|사망한 환자의 수|
|percentage|float|감염률|

<div name='II-4'/>

### 반환 예시

```json
{
    "status": {
        "code": 200,
        "message": "Successfully loaded 1 rows."
    },
    "data": [{
        "timestamp": 1584162001,
        "announced_timestamp": 1015113600,
        "increased": 107,
        "certified": 8086,
        "deisolated": 714,
        "dead": 72,
        "percentage": 15.6
    }]
}
```

```json
{
    "status": {
        "code": 200,
        "message": "Successfully loaded 1 rows."
    },
    "data": [{
        "timestamp": 1584162001,
        "announced_timestamp": 1015113600,
        "increased": 13,
        "certified": 238,
        "deisolated": 44,
        "dead": 0,
        "percentage": 2.45
    }]
}
```

<div name='II'/>

## III. 국외 환자수

**API 주소** : **`GET`** https://api.dropper.tech/covid19/status/global

**API 설명** : 외국 COVID19 환자수를 제공합니다.

<div name='III-1'/>

### 요청 값 속성

|속성|자료형|필수|설명|
|:-:|:-:|:-:|:-:|
|locale|string|Yes|조회하고자 하는 국가명|

<div name='III-2'/>

### 지원 국가

|값|설명|
|synthesize|합계|
|falklandislands|포클랜드제도|
|caribbeannetherlands|카리브 네덜란드|
|northernmarianaislands|북마리아나제도|
|britishvirginislands|영국령 버진아일랜드|
|angula|앵귈라|
|turksandcaicosislands|터크스 케이커스 제도|
|isleofman|맨섬|
|greenland|그린랜드|
|newcaledonia|뉴칼레도니아|
|montserrat|몬트세라트|
|sintmaartin|신트마르틴|
|bermuda|버뮤다|
|aruba|아루바|
|unitedstatesvirginislands|미국령 버진아일랜드|
|guam|괌|
|puertorico|푸에르토리코|
|mayotte|마요트|
|curacao|퀴라소|
|cayman|케이맨제도|
|guadeloupe|과들루프|
|regionreunion|프랑스령 레위니옹|
|jersey|저지섬|
|polynesia|프랑스령 폴리네시아|
|guernsey|건지섬|
|faroeislands|패로제도|
|guyane|프랑스령 기아나|
|martinique|마르티니크|
|vatican|바티칸|
|saintbarthelemy|생바르텔레미|
|saintmartin|세인트마틴|
|gibraltar|지브롤터|
|palestine|팔레스타인 |
|japan_cruise|일본 크루즈|
|sainttomeprincipe|상투메 프린시페|
|southsudan|남수단|
|malawi|말라위|
|sierraleone|시에라리온|
|burundi|브룬디|
|botswana|보츠와나|
|marley|말리|
|guineabissau|기니비사우|
|mozambique|모잠비크|
|uganda|우간다|
|eritrea|에리트레아|
|angola|앙골라|
|madagascar|마다가스카르|
|zimbabwe|짐바브웨|
|capeverde|카보베르데|
|somalia|소말리아|
|niger|니제르|
|chad|차드|
|zambia|잠비아|
|gambia|감비아|
|mauritius|모리셔스|
|djibouti|지부티|
|tanzania|탄자니아|
|liberia|라이베리아|
|benin|베냉|
|seychelles|세이쉘|
|rwanda|르완다|
|mauritania|모리타니아|
|eswatini|에스와티니|
|guinea|적도기니|
|congo|콩고|
|centralafricanrepublic|중앙아프리카공화국|
|namibia|나미비아|
|kenya|케냐|
|guineaecuatorial|기니|
|ghana|가나|
|gabon|가봉|
|ethiopia|에티오피아|
|sudan|수단|
|ivorycoast|코트디부아르|
|drcongo|DR콩고|
|burkinafaso|부르키나파소|
|republiquetogolaise|토고|
|republicofsouthafrica|남아프리카공화국|
|cameroon|카메룬|
|senegal|세네갈|
|nigeria|나이지리아|
|papuanewguinea|파푸아뉴기니|
|fiji|피지|
|newzealand|뉴질랜드|
|australia|호주|
|kosovo|코소보|
|montenegro|몬테네그로|
|turkey|터키|
|cyprus|사이프러스|
|albania|알바니아|
|moldova|몰도바|
|malta|몰타|
|bulgaria|불가리아|
|slovakia|슬로바키아|
|serbia|세르비아|
|liechtenstein|리히텐슈타인|
|slovenija|슬로베니아|
|bosnaihercegovina|보스니아 헤르체고비나|
|hungary|헝가리|
|ukraine|우크라이나|
|poland|폴란드|
|andora|안도라|
|latvia|라트비아|
|portugal|포르투갈|
|czecho|체코|
|ireland|아일랜드|
|armenia|아르메니아|
|luxembourg|룩셈부르크|
|monaco|모나코|
|iceland|아이슬란드|
|azerbaijan|아제르바이잔|
|sanmarino|산마리노|
|lithuania|리투아니아|
|belarus|벨라루스|
|nederlands|네덜란드|
|romania|루마니아|
|norway|노르웨이|
|macedonia|북마케도니아|
|greece|그리스|
|georgia|조지아|
|eesti|에스토니아|
|danmark|덴마크|
|belgium|벨기에|
|swiss|스위스|
|sweden|스웨덴|
|finland|핀란드|
|croatia|크로아티아|
|austria|오스트리아|
|spain|스페인|
|england|영국|
|france|프랑스|
|germany|독일|
|italiana|이탈리아|
|saintkittsandnevis|세인트키츠네비스|
|dominicanfederation|도미니카연방|
|belize|벨리즈|
|grenada|그레나다|
|haiti|아이티|
|nicaragua|니카라구아|
|barbados|바베이도스|
|elsalvador|엘살바도르|
|bahamas|바하마|
|guatemala|과테말라|
|suriname|수리남|
|saintlucia|세인트루시아|
|uruguay|우루과이|
|trinidadandtobago|트리니다드토바고|
|antiguaandbarbuda|앤티가바부다|
|venezuela|베네수엘라|
|guyana|가이아나|
|cuba|쿠바|
|stvincentandthegrenadines|세인트빈센트그레나딘|
|honduras|온두라스|
|jamaica|자메이카|
|bolivia|볼리비아|
|panama|파나마|
|paraguay|파라과이|
|costarica|코스타리카|
|peru|페루|
|columbia|콜롬비아|
|chile|칠레|
|argentina|아르헨티나|
|dominican|도미니카공화국|
|ecuador|에콰도르|
|mexico|멕시코|
|brasil|브라질|
|canada|캐나다|
|usa|미국|
|libya|리비아|
|syria|시리아|
|morocco|모로코|
|saudiarabia|사우디아라비아|
|tunisia|튀니지|
|jordan|요르단|
|qatar|카타르|
|algeria|알제리|
|egypt|이집트|
|israel|이스라엘|
|lebanon|레바논|
|oman|오만|
|iraq|이라크|
|uae|아랍에미리트|
|bahrain|바레인|
|kuwait|쿠웨이트|
|iran|이란|
|laos|라오스|
|myanmar|미얀마|
|easttimor|동티모르|
|kyrgyzstan|키르기스스탄|
|uzbekistan|우즈베키스탄|
|kazakhstan|카자흐스탄|
|mongolia|몽골|
|brunei|브루나이|
|bangladesh|방글라데시|
|maldives|몰디브|
|bhutan|부탄|
|indonesia|인도네시아|
|pakistan|파키스탄|
|afghanistan|아프가니스탄|
|srilanka|스리랑카|
|russia|러시아|
|nepal|네팔|
|cambodia|캄보디아|
|philippines|필리핀|
|india|인도|
|vietnam|베트남|
|malaysia|말레이시아|
|thailand|태국|
|singapura|싱가포르|
|japan|일본|
|macau|마카오|
|taiwan|대만|
|hongkong|홍콩|
|china|중국|

<div name='III-3'/>

### 반환 필드

|속성|자료형|설명|
|:-:|:-:|:-:|
|timestamp|int|데이터를 가져온 시점|
|increased|int|늘어난 환자의 수|
|certified|int|확진된 환자의 수|
|dead|int|사망한 환자의 수|

<div name='III-4'/>

### 반환 예시

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