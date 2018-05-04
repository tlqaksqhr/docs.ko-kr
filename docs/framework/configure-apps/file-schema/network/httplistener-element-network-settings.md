---
title: '&lt;httpListener&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a327f757f26c815d5b2cffe179af68bbe3d152eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;httpListener&gt; 요소 (네트워크 설정)
사용 하는 매개 변수를 사용자 지정은 <xref:System.Net.HttpListener> 클래스입니다.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<httpListener >  
  
## <a name="syntax"></a>구문  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>형식  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|unescapeRequestUrl|여부를 나타내는 부울 값을 한 <xref:System.Net.HttpListener> 인스턴스 변환된 URI 대신 원시 언 이스케이프 된 URI를 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
 **unescapeRequestUrl** 특성을 나타내는 경우 <xref:System.Net.HttpListener> 모든 퍼센트 인코딩 값이 변환 되 고 다른 정규화 단계가 수행 되는 변환된 URI 대신 원시 언 이스케이프 된 URI를 사용 합니다.  
  
 때는 <xref:System.Net.HttpListener> 인스턴스 통해 요청을 받을 `http.sys` 에서 제공 하 고 URI 문자열의 인스턴스를 만들고 서비스를 `http.sys`,으로 노출 된 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> 속성입니다.  
  
 `http.sys` 서비스는 두 요청 URI 문자열을 노출 합니다.  
  
-   원시 URI  
  
-   변환 된 URI  
  
 Uri의 원시는 <xref:System.Uri?displayProperty=nameWithType> HTTP 요청의 요청 줄에 제공 합니다.  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 제공 된 URI의 원시 `http.sys` 위에서 설명한 요청은 "/ 경로 /"에 대 한 합니다. 이 네트워크를 통해 전송 된 HTTP 동사를 다음 문자열을 나타냅니다.  
  
 `http.sys` 을 전달 해야 하는 원본 서버에서 요청을 확인 하려면 호스트 헤더 및 서비스는 HTTP 요청에서에서 제공 하는 URI를 사용 하 여 요청에 제공 된 정보에서 변환된 된 URI를 만듭니다. 이 등록 된 URI 접두사를 사용 하 여 요청에서 정보를 비교 하 여 수행 됩니다. HTTP 서버 SDK 설명서 HTTP_COOKED_URL 구조는 변환 된이 URI를 나타냅니다.  
  
 등록 된 URI 접두사를 사용 하 여 요청을 비교할 수 있도록 요청에 일부 정규화를 수행 해야 합니다. 위의 샘플 변환 된 URI에 대 한 것 같습니다.  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` 결합 하 여 서비스는 <xref:System.Uri.Host%2A?displayProperty=nameWithType> 속성 값과 변환된 된 URI를 만드는 요청 줄에 있는 문자열입니다. 또한 `http.sys` 및 <xref:System.Uri?displayProperty=nameWithType> 클래스는 다음을 수행 합니다.  
  
-   이스케이프 해제 인코딩된 모든 백분율 값입니다.  
  
-   비 ASCII 문자를 utf-16 문자 표현으로 퍼센트 인코딩 변환 합니다. Note u t F-8과 ANSI/DBCS 문자가 유니코드 문자 (유니코드 %uXXXX 형식을 사용 하 여 인코딩)도 지원 됩니다.  
  
-   경로 압축 같은 다른 정규화 단계를 실행합니다.  
  
 퍼센트 인코딩 값에 사용 되는 인코딩에 대 한 정보가 요청 없으므로 퍼센트 인코딩 값을 구문 분석 하 여 올바른 인코딩을 확인할 못할 수 있습니다.  
  
 따라서 `http.sys` 프로세스를 수정 하기 위한 두 개의 레지스트리 키를 제공 합니다.  
  
|레지스트리 키|기본값|설명|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|0 이면 `http.sys` u t F-8로 인코딩된 Url만 허용 합니다.<br /><br /> 0이 아닌 경우 `http.sys` 도 요청에서 ANSI로 인코딩된 또는 DBCS 인코딩된 Url을 허용 합니다.|  
|FavorUTF8|1|0이 아닌 경우 `http.sys` 디코딩할 URL u t F-8로 먼저 해당 변환이 실패 하 고 EnableNonUTF8 0이 아닌 경우 하려고 항상 차례로 Http.sys을 ANSI 또는 DBCS 디코딩할 하려고 합니다.<br /><br /> 0 (및 EnableNonUTF8 0이 아닌) `http.sys` 경우 해당 ANSI 또는 DBCS; 디코딩하 려 성공 하지 못하면, 시도 u t F-8로 변환 합니다.|  
  
 때 <xref:System.Net.HttpListener> 한 요청을 받으면에서 변환 된 URI를 사용 하 여 `http.sys` 대 한 입력으로 <xref:System.Net.HttpListenerRequest.Url%2A> 속성입니다.  
  
 Uri에서 문자 및 숫자 이외의 문자를 지원할 필요가 있습니다. 예로 고객에 대 한 고객 정보를 검색 하는 데 사용 되는 다음 URI는 번호 "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Uri (%2F)에서 % 인코딩된 슬래시를 note 합니다. 이 작업은 슬래시 문자 데이터 및 하지는 경로 구분 기호를 나타내므로 경우에 필요 합니다.  
  
 Uri 생성자에 문자열을 전달 하면 다음과 같은 uri를 일으킵니다.  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 경로를 세그먼트로 분할 하면 다음과 같은 요소가 만들어집니다.  
  
 `Customer('1`  
  
 `3812')`  
  
 요청을 보낸 사람 의도 아닙니다.  
  
 경우는 **unescapeRequestUrl** 특성이로 설정 된 **false**, 다음 경우는 <xref:System.Net.HttpListener> 한 요청을 받으면 원시 URI에서 변환 된 URI 대신 사용 하 여 `http.sys` 는 에입력으로<xref:System.Net.HttpListenerRequest.Url%2A> 속성입니다.  
  
 기본값은 **unescapeRequestUrl** 특성은 **true**합니다.  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 속성의 현재 값을 가져오는 데 사용할 수는 **unescapeRequestUrl** 해당 구성 파일에서 특성입니다.  
  
## <a name="example"></a>예제  
 구성 하는 방법을 보여 주는 다음 예제는 <xref:System.Net.HttpListener> 대신 변환 된 URI에서 원시 URI를 사용 하는 요청을 받을 때 클래스 `http.sys` 대 한 입력으로 <xref:System.Net.HttpListenerRequest.Url%2A> 속성입니다.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||
|-|-|  
|네임스페이스|System.Net|  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있습니다.||  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
