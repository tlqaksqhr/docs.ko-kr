---
title: WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 3206947d06a1736116674b70e469c20f8f4fca86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)
DataSvcUtil.exe는에서 제공 하는 명령줄 도구 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 을 사용 하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드 하 고.NET Framework 클라이언트 응용 프로그램에서 데이터 서비스에 액세스 하는 데 필요한 클라이언트 데이터 서비스 클래스를 생성 합니다. 이 유틸리티는 다음 메타데이터 소스를 사용하여 데이터 클래스를 생성할 수 있습니다.  
  
-   데이터 서비스의 루트 URI 이 유틸리티는 데이터 서비스에서 노출하는 데이터 모델을 설명하는 서비스 메타데이터 문서를 요청합니다. 자세한 내용은 참조 [OData: 서비스 메타 데이터 문서](http://go.microsoft.com/fwlink/?LinkId=186070)합니다.  
  
-   에 정의 된 개념 스키마 정의 언어 (CSDL)을 사용 하 여 정의 된 데이터 모델 파일 (.csdl)는 [ \[MC-CSDL\]: 개념 스키마 정의 파일 형식](http://go.microsoft.com/fwlink/?LinkID=159072) 사양입니다.  
  
-   Entity Framework와 함께 제공되는 엔터티 데이터 모델 도구를 사용하여 만든 .edmx 파일. 자세한 내용은 참조는 [ \[MC-EDMX\]: 데이터 서비스 패키징 형식의 엔터티 데이터 모델](http://go.microsoft.com/fwlink/?LinkID=178833) 사양입니다.  
  
 자세한 내용은 참조 [하는 방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)합니다.  
  
 DataSvcUtil.exe 도구는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 디렉터리에 설치됩니다. 대체로 이 도구는 C:\Windows\Microsoft.NET\Framework\v4.0에 있으며 64비트 시스템의 경우 C:\Windows\Microsoft.NET\Framework64\v4.0에 있습니다. Visual Studio 명령 프롬프트에서 DataSvcUtil.exe 도구에 액세스할 수도 있습니다 (클릭 **시작**, 가리킨 **모든 프로그램**, 가리킨 **Microsoft Visual Studio 2010**, 가리킨 **Visual Studio Tools**, 클릭 하 고 **Visual Studio 2010 명령 프롬프트**).  
  
## <a name="syntax"></a>구문  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|옵션|설명|  
|------------|-----------------|  
|`/dataservicecollection`|개체를 컨트롤에 바인딩하는 데 필요한 코드도 생성되도록 지정합니다.|  
|`/help`<br /><br /> 또는<br /><br /> `/?`|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|`/in:` *\<파일 >*|.csdl 또는 .edmx 파일이나 파일이 있는 디렉터리를 지정합니다.|  
|`/language:`[VB&#124;CSharp]|생성되는 소스 코드 파일의 언어를 지정합니다. 기본 언어는 C#입니다.|  
|`/nologo`|저작권 메시지가 표시되지 않도록 합니다.|  
|`/out:` *\<파일 >*|생성된 클라이언트 데이터 서비스 클래스가 포함되는 소스 코드 파일의 이름을 지정합니다.|  
|`/uri:` *\<문자열 >*|URI는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드입니다.|  
|`/version:`[1.0&#124;2.0]|허용되는 최고 버전의 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]을 지정합니다. 버전에 따라 결정 되는 `DataServiceVersion` 반환 되는 데이터 서비스 메타 데이터에 있는 DataService 요소의 특성입니다. 자세한 내용은 참조 [데이터 서비스 버전 관리](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)합니다. 지정 하는 경우는 `/dataservicecollection` 매개 변수를 지정 해야 `/version:2.0` 데이터 바인딩을 사용할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
