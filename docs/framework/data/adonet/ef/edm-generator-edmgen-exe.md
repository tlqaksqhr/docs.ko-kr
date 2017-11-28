---
title: "EDM 생성기(EdmGen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: da99c43d9142ee754b2b48db45ca070d1ab7c4e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="edm-generator-edmgenexe"></a>EDM 생성기(EdmGen.exe)
EdmGen.exe는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 모델 및 매핑 파일 작업에 사용되는 명령줄 도구입니다. EdmGen.exe 도구를 사용하여 다음을 수행할 수 있습니다.  
  
-   데이터 소스 관련 .NET Framework 데이터 공급자를 사용하여 데이터 소스에 연결하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서 사용되는 개념적 모델(.csdl), 저장소 모델(.ssdl) 및 매핑(.msl) 파일을 생성합니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.  
  
-   기존 모델의 유효성을 검사합니다. 자세한 내용은 참조 [하는 방법: 모델 유효성 검사 및 매핑 파일을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)합니다.  
  
-   개념적 모델(.csdl) 파일에서 생성된 개체 클래스가 포함되는 C# 또는 Visual Basic 코드 파일을 생성합니다. 자세한 내용은 참조 [하는 방법: 개체 계층 코드 생성을 사용 하 여 EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)합니다.  
  
-   기존 모델에 대해 미리 생성된 뷰가 들어 있는 C# 또는 Visual Basic 코드 파일을 생성합니다. 자세한 내용은 [하는 방법: 쿼리 성능이 향상 Pre-Generate 뷰](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)합니다.  
  
 EdmGen.exe 도구는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 디렉터리에 설치됩니다. 대체로 이 도구는 C:\windows\Microsoft.NET\Framework\v4.0에 있으며 64비트 시스템의 경우 C:\windows\Microsoft.NET\Framework64\v4.0에 있습니다. Visual Studio 명령 프롬프트에서 EdmGen.exe 도구에 액세스할 수도 있습니다 (클릭 **시작**, 가리킨 **모든 프로그램**, 가리킨 **Microsoft Visual Studio 2010**를 가리키고 **Visual Studio Tools**, 클릭 하 고 **Visual Studio 2010 명령 프롬프트**).  
  
## <a name="syntax"></a>구문  
  
```  
EdmGen /mode:choice [options]  
```  
  
## <a name="mode"></a>모드  
 EdmGen.exe 도구를 사용하는 경우 다음 모드 중 하나를 지정해야 합니다.  
  
|모드|설명|  
|----------|-----------------|  
|`/mode:ValidateArtifacts`|.csdl, .ssdl 및 .msl 파일의 유효성을 검사하고 오류 또는 경고를 표시합니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl` 또는 `/incsdl` 인수 중 하나 이상이 필요합니다. `/inmsl`을 지정하면 `/inssdl` 및 `/incsdl` 인수도 필요합니다.|  
|`/mode:FullGeneration`|`/connectionstring` 옵션에 지정된 데이터베이스 연결 정보를 사용하고 .csdl, .ssdl, .msl, 개체 계층 및 뷰 파일을 생성합니다.<br /><br /> 이 옵션을 사용하려면 `/connectionstring` 인수와 `/project` 인수 또는 `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` 및 `/entitycontainer` 인수 중 하나가 필요합니다.|  
|`/mode:FromSSDLGeneration`|지정한 .ssdl 파일에서 .csdl 및 .msl 파일, 소스 코드 및 뷰를 생성합니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl` 인수와 `/project` 인수 또는 `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` 및 `/entitycontainer` 인수 중 하나가 필요합니다.|  
|`/mode:EntityClassGeneration`|.csdl 파일에서 생성된 클래스가 포함되는 소스 코드 파일을 만듭니다.<br /><br /> 이 옵션을 사용하려면 `/incsdl` 인수와 `/project` 인수 또는 `/outobjectlayer` 인수가 필요합니다. `/language` 인수는 선택적 요소입니다.|  
|`/mode:ViewGeneration`|.csdl, .ssdl 및 .msl 파일에서 생성된 뷰가 포함되는 소스 코드 파일을 만듭니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl`, `/incsdl`, `/inmsl,` 인수와 `/project` 또는 `/outviews` 인수가 필요합니다. `/language` 인수는 선택적 요소입니다.|  
  
## <a name="options"></a>옵션  
  
|옵션|설명|  
|------------|-----------------|  
|`/p[roject]:`\<문자열 >|사용할 프로젝트 이름을 지정합니다. 프로젝트 이름은 네임스페이스 설정, 모델 및 매핑 파일 이름, 개체 소스 파일 이름, 뷰 생성 소스 파일 이름의 기본값으로 사용됩니다. 엔터티 컨테이너 이름으로 설정 됩니다 \<프로젝트 > 컨텍스트.|  
|`/prov[ider]:`\<문자열 >|저장소 모델(.ssdl) 파일을 생성하는 데 사용할 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 데이터 공급자의 이름입니다. 기본 공급자는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|  
|`/c[onnectionstring]:`\<연결 문자열 >|데이터 소스에 연결하는 데 사용되는 문자열을 지정합니다.|  
|`/incsdl:`\<파일 >|.csdl 파일 또는 .csdl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .csdl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 디렉터리를 지정하면 개념적 모델이 몇 개의 파일에 분할되어 있을 때 클래스(`/mode:EntityClassGeneration`) 또는 뷰(`/mode:ViewGeneration`)를 생성하는 데 유용할 수 있습니다. 여러 모델(`/mode:ValidateArtifacts`)의 유효성을 검사하려는 경우에도 유용할 수 있습니다.|  
|`/refcsdl:`\<파일 >|소스 .csdl 파일의 참조를 확인하는 데 사용되는 추가 .csdl 파일을 지정합니다. 소스 .csdl 파일은 `/incsdl` 옵션으로 지정된 파일입니다. `/refcsdl` 파일에는 소스 .csdl 파일이 종속된 형식이 들어 있습니다. 이 인수를 여러 번 지정할 수 있습니다.|  
|`/inmsl:`\<파일 >|.msl 파일 또는 .msl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .msl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 디렉터리를 지정하면 개념적 모델이 몇 개의 파일에 분할되어 있을 때 뷰(`/mode:ViewGeneration`)를 생성하는 데 유용할 수 있습니다. 여러 모델(`/mode:ValidateArtifacts`)의 유효성을 검사하려는 경우에도 유용할 수 있습니다.|  
|`/inssdl:`\<파일 >|.ssdl 파일 또는 .ssdl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .ssdl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 모델`(/mode:ValidateArtifacts)`의 유효성을 검사하려는 경우에 유용할 수 있습니다.|  
|`/outcsdl:`\<파일 >|만들 .csdl 파일의 이름을 지정합니다.|  
|`/outmsl:`\<파일 >|만들 .msl 파일의 이름을 지정합니다.|  
|`/outssdl:`\<파일 >|만들 .ssdl 파일의 이름을 지정합니다.|  
|`/outobjectlayer:`\<파일 >|.csdl 파일에서 생성된 개체가 포함되는 소스 코드 파일의 이름을 지정합니다.|  
|`/outviews:`\<파일 >|생성된 뷰가 포함되는 소스 코드 파일의 이름을 지정합니다.|  
|`/language:`[VB &#124; CSharp]|생성되는 소스 코드 파일의 언어를 지정합니다. 기본 언어는 C#입니다.|  
|`/namespace:`\<문자열 >|사용할 모델 네임스페이스를 지정합니다. 네임스페이스는 `/mode:FullGeneration` 또는 `/mode:FromSSDLGeneration`을 실행할 때 .csdl 파일에서 설정됩니다. `/mode:EntityClassGeneration`을 실행할 때는 네임스페이스가 사용되지 않습니다.|  
|`/entitycontainer:`\<문자열 >|생성되는 모델 및 매핑 파일의 `<EntityContainer>` 요소에 적용할 이름을 지정합니다.|  
|`/pl[uralize]`|개념적 모델의 `Entity`, `EntitySet` 및 `NavigationProperty` 이름에 영어의 단수 및 복수 규칙을 적용합니다. 이 옵션은 다음 동작을 수행합니다.<br /><br /> -모든 확인 `EntityType` 이름을 단 수 화 합니다.<br />-모든 확인 `EntitySet` 이름을 복수화 합니다.<br />-각각에 대해 `NavigationProperty` 를 최대 하나의 엔터티를 반환 하는 이름을 단 수 있도록 합니다.<br />-각각에 대해 `NavigationProperty` 를 둘 이상의 엔터티를 반환 하는 경우 이름을 복수화 합니다.|  
|`/SupressForeignKeyProperties or /nofk`|외래 키 열이 개념적 모델의 엔터티 형식에 대한 스칼라 속성으로 노출되지 않도록 합니다.|  
|`/help` 또는 `?`|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|`/nologo`|저작권 메시지가 표시되지 않도록 합니다.|  
|`/targetversion:`\<문자열 >|생성된 코드를 컴파일하는 데 사용할 .NET Framework 버전입니다. 지원되는 버전은 4 및 4.5입니다. 기본값은 4입니다.|  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)  
  
 [방법: EdmGen.exe를 사용 하 여 개체 계층 코드를 생성 하려면](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)  
  
 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 유효성을 검사 하려면](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 엔터티 데이터 모델 도구](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [엔터티 데이터 모델](../../../../../docs/framework/data/adonet/entity-data-model.md)  
 [CSDL, SSDL 및 MSL 사양](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
