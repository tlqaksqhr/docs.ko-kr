---
title: "데스크톱 응용 프로그램의 리소스 패키징 및 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 배포[.NET Framework], 리소스"
  - "리소스 파일, 배포"
  - "허브 및 스포크 리소스 배포 모델"
  - "리소스 파일, 패키징"
  - "응용 프로그램 리소스, 패키징"
  - "단일 리소스 어셈블리"
  - "위성 어셈블리"
  - "응용 프로그램의 기본 culture"
  - "이름[.NET Framework], 리소스"
  - "리소스의 대체(fallback) 프로세스"
  - "culture 그룹화"
  - "응용 프로그램 리소스, 배포"
  - "응용 프로그램 리소스, 명명 규칙"
  - "문화권, 리소스 패키징 및 배포"
  - "리소스 파일, 명명 규칙"
  - "응용 프로그램 리소스 패키징"
  - "응용 프로그램 리소스, 대체 프로세스"
  - "리소스 파일, 대체 프로세스"
  - "리소스 지역화"
  - "중립 문화권"
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# 데스크톱 응용 프로그램의 리소스 패키징 및 배포
응용 프로그램은 지역화된 리소스를 검색하기 위해 <xref:System.Resources.ResourceManager> 에 의해 나타난 .NET Framework Resource Manager에 의존합니다.  리소스 관리자는 허브 및 스포크 모델을 패키지 하고 리소스를 배포 하는 데 사용 된다고 가정 합니다.  허브는 지역화할 수 없는 실행 코드와 중립 또는 기본 문화권이라고 하는 단일 문화권의 리소스를 포함하는 주 어셈블리입니다.  기본 문화권은 응용 프로그램에 대한 대체 문화권입니다; 지역화 된 리소스를 찾을 수 없는 경우 해당 리소스를 사용 하는 문화권입니다.  각 스포크는 단일 문화권의 리소스를 포함하지만 코드는 포함하지 않는 위성 어셈블리에 연결됩니다.  
  
 이 모델은 다음과 같은 몇 가지 장점을 가집니다.  
  
-   응용 프로그램을 배포한 후 새 문화권에 대해 리소스를 점진적으로 추가할 수 있습니다.  문화권별 리소스의 다음 번 배포에는 상당한 시간이 필요하므로 이 모델을 사용하면 주 응용 프로그램을 먼저 릴리스하고 나중에 문화권별 리소스를 전달할 수 있습니다.  
  
-   응용 프로그램을 다시 컴파일하지 않고 응용 프로그램의 위성 어셈블리를 업데이트 및 변경할 수 있습니다.  
  
-   응용 프로그램은 특정 문화권에 필요한 리소스를 포함하는 위성 어셈블리만 로드해야 합니다.  이렇게 하면 시스템 리소스 사용을 상당히 줄일 수 있습니다.  
  
 그러나 다음과 같이 이 모델 사용에 따른 단점도 있습니다.  
  
-   여러 개의 리소스 집합을 관리해야 합니다.  
  
-   여러 개의 구성을 테스트해야 하므로 응용 프로그램 테스트의 초기 비용이 높습니다.  장기적으로 볼 때 여러 개의 동일한 국가별 버전을 테스트하고 유지 관리하는 것보다는 위성 어셈블리가 여러 개 있는 하나의 핵심 응용 프로그램을 테스트하는 것이 더 쉽고 비용도 적게 듭니다.  
  
## 리소스 명명 규칙  
 응용 프로그램의 리소스를 패키지하는 경우 공용 언어 런타임에서 예상하는 리소스 명명 규칙을 사용하여 리소스 이름을 지정해야 합니다.  런타임은 문화권 이름으로 리소스를 식별합니다.  각 문화권에는 고유한 이름이 지정됩니다. 이 이름은 보통 언어와 관련된 두 자의 소문자 문화권 이름과 필요한 경우 국가 또는 지역과 관련된 두 자의 대문자 하위 문화권 이름의 조합입니다.  하위 culture 이름은 culture 이름 뒤에 오며 대시\(\-\)로 구분됩니다.  예는 일본에서 말하는 일본인을 위한 JA\-JP, 미국에서 말하는 미국인을 위한 EN\-US와, 독일에서 말하는 독일인을 위한 DE\-DE, 또는 오스트리아에서 독일어 de\-AT를 포함합니다.  전체 문화권 이름 목록은 Go Global Developer Center의 [National Language Support \(NLS\) API Reference](http://go.microsoft.com/fwlink/?LinkId=200048)를 참조하십시오.  
  
> [!NOTE]
>  리소스 파일을 만드는 방법에 대한 내용은 MSDN Library에서 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md) 와[위성 어셈블리 만들기](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) 를 참조하십시오.  
  
<a name="cpconpackagingdeployingresourcesanchor1"></a>   
## 리소스 대체 프로세스  
 리소스 패키징 및 배포를 위한 허브와 스포크 모델은 대체 프로세스를 사용하여 적절한 리소스를 찾습니다.  사용할 수 없는 지약화된 리소스를 응용 프로그램이 요청하면, 공용 언어 런타임은 사용자의 응용 프로그램의 요청과 가장 근접하게 일치하는 적절한 대체 리소스를 위해 문화권 계층 구조를 검색하고 이러한 대체 리소스가 없는 경우에만 예외를 발생시킵니다.  계층의 각 수준에서 적절한 리소스를 찾으면 런타임에서는 해당 리소스를 사용하고  리소스를 찾지 못하면 다음 수준에서 계속 검색합니다.  
  
 찾기 성능을 향상시키려면 <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성을 주 어셈블리에 적용하고 주 어셈블리에서 사용할 중립 언어의 이름을 이 특성에 전달합니다.  
  
> [!TIP]
>  리소스 어셈블리를 위해 런타임이 조사하는 과정과 리소스 대체 과정을 최적화하기 위해 [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) 구성 요소를 사용할 수 있습니다.  자세한 내용은  [리소스 대체 프로세스 최적화](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#Optimizing) 단원을 참조하십시오.  
  
 리소스 대체 프로세스는 다음 단계를 포함합니다.  
  
1.  런타임에서는 먼저 [global assembly cache](../../../docs/framework/app-domains/gac.md) 를 검사하여 응용 프로그램에 대해 요청된 문화권과 일치하는 어셈블리를 찾습니다.  
  
     전역 어셈블리 캐시는 여러 응용 프로그램에서 공유하는 리소스 어셈블리를 저장할 수 있습니다.  이렇게 하면 사용자가 만드는 모든 응용 프로그램의 디렉터리 구조에 특정 리소스 집합을 포함할 필요가 없습니다.  런타임에서 어셈블리에 대한 참조를 찾으면 요청된 리소스가 있는지 해당 어셈블리를 검색합니다.  어셈블리에서 엔트리를 찾으면 요청된 리소스를 사용하고  엔트리를 찾지 못하면 검색을 계속합니다.  
  
2.  그런 다음 런타임에서는 현재 실행 중인 어셈블리의 디렉터리를 검사하여 요청된 문화권과 일치하는 디렉터리인지 확인합니다.  디렉터리를 찾으면 요청된 문화권에 대해 올바른 위성 어셈블리가 있는지 해당 디렉터리를 검색합니다.  그런 다음 런타임에서는 요청된 리소스가 있는지 위성 어셈블리를 검색합니다.  어셈블리에서 리소스를 찾으면 이것을 사용하고  리소스를 찾지 못하면 검색을 계속합니다.  
  
3.  런타임에서 다음 위성 어셈블리 필요에 따라 설치할 수 있는지 확인 하려면 Windows Installer를 쿼리 합니다.  그렇다면, 설치를 처리하고, 어셈블리를 로드하고, 요청된 리소스를 검색 합니다.  어셈블리에서 리소스를 찾으면 이것을 사용하고  리소스를 찾지 못하면 검색을 계속합니다.  
  
4.  위성 어셈블리를 찾을 수 없을 때 표시하기 위해 런타임은 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 발생시킵니다.  이벤트를 처리 하는 경우, 이벤트 처리기는 조회에 사용할 리소스인 위성 어셈블리에 대한 참조를 반환할 수 있습니다.  그렇지 않으면, 이벤트 처리기는 `null` 을 반환하고 계속 검색합니다.  
  
5.  그런 다음 런타임은 다시 전역 어셈블리 캐시를 검색하는데 이번에는 요청된 문화권의 부모 어셈블리를 찾습니다.  전역 어셈블리 캐시에 부모 어셈블리가 있으면 런타임에서는 요청된 리소스가 있는지 어셈블리를 검색합니다.  
  
     부모 문화권은 적절한 대체 문화권으로 정의됩니다.  부모 어셈블리를 대체 후보로 고려하십시오. 왜냐하면 어떤 것이든 리소스를 제공하는 것이 예외를 throw하는 것보다는 좋기 때문입니다.  또한 이 프로세스를 사용하면 리소스를 다시 사용할 수 있습니다.  자식 문화권에서 요청된 리소스를 지역화할 필요가 없는 경우에만 부모 수준에서 특정 리소스를 포함해야 합니다.  예를 들어 en\(중립 영어\), en\-GB\(영국식 영어\) 및 en\-US\(미국식 영어\)에 대해 위성 어셈블리를 제공하면, en 위성은 공용 용어를 포함하고, en\-GB와 en\-US 위성은 그 외의 다른 용어에 대해서만 재정의할 수 있습니다.  
  
6.  그런 다음 런타임에서는 현재 실행 중인 어셈블리의 디렉터리를 검사하여 부모 디렉터리를 포함하는지 확인합니다.  부모 디렉터리가 있으면 런타임에서는 부모 문화권에 대해 올바른 위성 어셈블리가 있는지 해당 디렉터리를 검색합니다.  어셈블리를 찾으면 런타임에서는 요청된 리소스가 있는지 해당 어셈블리를 검색합니다.  리소스를 찾으면 이것을 사용하고  리소스를 찾지 못하면 검색을 계속합니다.  
  
7.  런타임에서 다음 부모 위성 어셈블리가 필요에 따라 설치할 수 있는지 확인 하려면 Windows Installer를 쿼리 합니다.  그렇다면, 설치를 처리하고, 어셈블리를 로드하고, 요청된 리소스를 검색 합니다.  어셈블리에서 리소스를 찾으면 이것을 사용하고  리소스를 찾지 못하면 검색을 계속합니다.  
  
8.  적절한 대체 리소스를 찾지 못한 것을 나타내기 위해 런타임은 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>이벤트를 발생시킵니다.  이벤트를 처리 하는 경우, 이벤트 처리기는 조회에 사용할 리소스인 위성 어셈블리에 대한 참조를 반환할 수 있습니다.  그렇지 않으면, 이벤트 처리기는 `null` 을 반환하고 계속 검색합니다.  
  
9. 그런 다음 런타임에서는 이전 세 단계에서와 같이 가능한 여러 수준에서 부모 어셈블리를 검색합니다.  각 문화권에 의해 정의 되는 하나의 부모는 <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=fullName> 속성이 아니라 부모는 자신의 부모를 가집니다.  문화권의 <xref:System.Globalization.CultureInfo.Parent%2A> 속성이 리소스 대체를 위해 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 반환할 때 부모 문화권 검색이 멈추고, 변치 않는 문화권은 리소를 갖는 문화권 또는 부모 문화권으로 간주 되지 않습니다.  
  
10. 처음에 지정된 문화권과 모든 부모를 검색한 결과 리소스를 찾지 못한 경우 기본\(대체\) 문화권의 리소스가 사용됩니다.  일반적으로, 기본 문화권의 리소스를 주 응용 프로그램 어셈블리에 포함 합니다.  그러나, 리소스의 궁극적인 대체 위치가 주 어셈블리가 아닌 위성 어셈블리임을 나타내기 위해 <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성의 <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> 속성을 위한 <xref:System.Resources.UltimateResourceFallbackLocation> 값을 지정할 수 있습니다.  
  
    > [!NOTE]
    >  기본 리소스는 주 어셈블리와 함께 컴파일된 리소스뿐입니다.  위성 어셈블리를 <xref:System.Resources.NeutralResourcesLanguageAttribute>특성을 사용하여 지정하지 않으면, 최종 대체\(최종 부모\)가 됩니다.  그러므로, 주 어셈블리에 항상 기본 리소스 집합을 포함하는 것을 추천합니다.  이렇게 하면 예외가 throw 되지 않도록 합니다.  기본 리소스 파일을 포함시킴으로써, 사용자를 위한 적어도 하나 이상의 리소스\(특정 문화권에 관련되지는 않음\)가 항상 있도록 모든 리소스에 대한 대체를 제공할 수 있습니다.  
  
11. 마지막으로, 런타임이 기본\(대체\) 문화권의 리소스를 찾지 못하면, <xref:System.Resources.MissingManifestResourceException> 또는 <xref:System.Resources.MissingSatelliteAssemblyException> 예외가 리소스가 찾을 수 없는 것을 나타내기 위해 throw 됩니다.  
  
 예를 들어, 응용 프로그램이 스페인어 \(멕시코\) \(ES\-MX 문화권\)에 대한 지역화 된 리소스를 요청한다고 가정합니다.  런타임은 es\-MX와 일치하는 어셈블리의 먼저 전역 어셈블리 캐시를 찾지만, 찾을 수 없습니다.  런타임은 그 다음 "es\-MX" 디렉터리를 위해 현재 실행 중인 어셈블리의 디렉터리를 검색합니다.  실패하면, 런타임은 전역 어셈블리 캐시를 다시 검색하여 적절한 대체 문화권, 여기에서는 "es"\(스페인어\)를 반영하는 부모 어셈블리를 찾습니다.  부모 어셈블리를 찾지 못하면, 런타임은 부모 어셈블리의 가능한 모든 수준을 검색하여 해당하는 리소스를 찾을 때까지 "es\-MX" 문화권을 찾습니다.  리소스를 찾지 못하면, 런타임에서는 기본 문화권의 리소스를 사용합니다.  
  
<a name="Optimizing"></a>   
### 리소스 대체 프로세스 최적화  
 다음 조건에서, 위성 어셈블리의 리소스를 런타임에서 검색 하는 프로세스를 최적화할 수 있습니다.  
  
-   위성 어셈블리는 코드 어셈블리와 같은 위치에 배포 됩니다.  코드 어셈블리가 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)에서 설치되었다면, 위성 어셈블리는 전역 어셈블리에 설치 됩니다.  코드 어셈블리가 디렉터리에 설치 되어 있으면, 위성 어셈블리는 디렉터리의 문화권별 폴더에 설치 됩니다.  
  
-   요청 시 위성 어셈블리가 설치 되지 않습니다.  
  
-   응용 프로그램 코드는 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 처리 하지 않습니다.  
  
 [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) 와 다음 예제에서 보여진 것처럼 응용 프로그램 구성 파일에서 `enabled` 특성을 `true` 로 설정을 포함하여 위성 어셈블리 조사를 최적화 할 수 있습니다.  
  
```  
  
<configuration>  
   <runtime>  
      <relativeBindForResources enabled="true" />  
   </runtime>  
</configuration>  
  
```  
  
 위성 어셈블리에 대한 최적화 된 프로브는 옵트인 기능입니다.  즉, 런타임은 [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) 요소가 응용 프로그램의 구성 파일에 있고 `enabled` 특성이 `true`로 설정되어 있지 않으면 [리소스 대체 프로세스](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1) 에 설명된 단계를 따릅니다.  이 경우, 위성 어셈블리를 조사 하는 과정은 다음과 같이 수정 됩니다.  
  
-   런타임은 부모 코드 어셈블리의 위치를 사용하여 부모 코드 어셈블리에 대한 조사를 합니다.  부모 어셈블리를 전역 어셈블리 캐시에 설치 하면, 런타임은 응용 프로그램의 디렉터리가 아닌 캐시에서 조사합니다.  부모 어셈블리가 어셈블리 디렉토리에 설치 되면, 런타임은 전역 어셈블리 캐시가 아닌 응용 프로그램 디렉토리에서 조사합니다.  
  
-   런타임은 요청 시 위성 어셈블리 설치에 대한 Windows Installer 쿼리를 하지 않습니다.  
  
-   특정 리소스 어셈블리에 대한 조사가 실패 하면, 런타임은 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 발생시키지 않습니다.  
  
### 최종 대체\(Fallback\)를 위성 어셈블리로  
 선택적으로 주 어셈블리에서 리소스를 제거 하고 런타임이 최종 대체 \(fallback\) 리소스를 특정 문화권에 해당 하는 위성 어셈블리에서 로드 해야 함을 지정할 수 있습니다.  대체 \(fallback\) 프로세스를 제어 하기 위해, <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29?displayProperty=fullName> 생성자를 사용하고 리소스 관리자가 위성 어셈블리에서 또는 주 어셈블리에서 대체 리소스를 추출해야 함을 지정하는 <xref:System.Resources.UltimateResourceFallbackLocation> 매개 변수의 값을 제공합니다.  
  
 다음 예제는 <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성을 위성 어셈블리에서 불어\(fr\)로 응용 프로그램의 대체 리소스를 저장하기 위해 사용합니다.  이 예제는 `Greeting`로 명명된 단일 문자열 리소스를 정의하는 두 개의 텍스트 기반 리소스 파일을 갖습니다.  첫째 resources.fr.txt는 프랑스어 리소스를 포함 합니다.  
  
```  
Greeting=Bon jour!  
```  
  
 두 번째 resources,ru.txt는 러시아어 언어 리소스를 포함 합니다.  
  
```  
Greeting=Добрый день  
```  
  
 이 두 파일은 명령 줄에서 [resource file generator \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)을 실행하여 리소스 파일을 컴파일 될 수 있습니다.  프랑스어 리소스에서 명령은 다음과 같습니다.  
  
 **resgen.exe resources.fr.txt**  
  
 러시아어 리소스에서 명령은 다음과 같습니다.  
  
 **resgen.exe resources.ru.txt**  
  
 .Resources 파일은 다음과 같이 프랑스어 리소스를 위한 명령 줄로 부터 [assembly linker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 실행하여 동적 연결 라이브러리를 포함할 수 있습니다.  
  
 **al \/t:lib \/embed:resources.fr.resources \/culture:fr \/out:fr\\Example1.resources.dll**  
  
 그리고 러시아어 리소스는 다음과 같습니다:  
  
 **al \/t:lib \/embed:resources.ru.resources \/culture:ru \/out:ru\\Example1.resources.dll**  
  
 응용 프로그램 소스 코드는 Example1.cs 또는 Example1.vb 라는 파일에 저장 됩니다.  <xref:System.Resources.NeutralResourcesLanguageAttribute> 특성을 기본 응용 프로그램 리소스가 fr 하위 디렉터리에 있는 것을 나타내기 위해 포함합니다.  리소스 관리자를 인스턴스화하고, `Greeting` 리소스의 값을 검색하고 콘솔에 표시 합니다.  
  
 [!code-csharp[Conceptual.Resources.Packaging#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
 [!code-vb[Conceptual.Resources.Packaging#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]  
  
 다음 처럼 명령 줄에서 C\# 소스 코드를 컴파일할 수 있습니다.  
  
 **csc Example1.cs**  
  
 Visual Basic 컴파일러 명령은 매우 비슷합니다:  
  
 **vbc Example1.vb**  
  
 주 어셈블리에 포함 되는 리소스가 없으므로, `/resource` 전환을 이용하여 컴파일 할 필요가 없습니다.  
  
 러시아어 외의 언어가 시스템에서 이 예제를 실행 하면 다음과 같은 출력이 표시 됩니다.  
  
```  
Bon jour!  
```  
  
## 패키징 대체 방법 제안  
 시간이나 예산 제약 조건으로 인해 응용 프로그램에서 지원하는 모든 하위 문화권의 리소스 집합을 만들지 못할 수도 있습니다.  대신, 관련된 모든 하위 문화권에서 사용할 수 있는 부모 문화권에 대한 단일 위성 어셈블리를 만들 수 있습니다.  예를 들어, 국가별 영어 리소스를 요청하는 사용자에 의해 검색되는 영어 위성 어셈블리\(en\) 하나와 국가별 독일어 리소스를 요청하는 사용자를 위해 독일어 위성 어셈블리\(de\) 하나를 제공할 수 있습니다.  예를 들어, 독일에서 사용하는 독일어\(de\-DE\), 오스트리아에서 사용하는 독일어\(de\-AT\) 및 스위스에서 사용하는 독일어\(de\-CH\)를 요청하면 독일어 위성 어셈블리\(de\)로 대체됩니다.  기본 리소스는 마지막 대체이므로 대부분의 응용 프로그램 사용자가 요청하는 리소스여야 합니다. 그러므로 이 리소스를 주의 깊게 선택합니다.  이 방법을 사용하면 문화권에 특정하지 않은 리소스가 배포된다 하더라도 응용 프로그램의 지역화 비용을 상당히 줄일 수 있습니다.  
  
## 참고 항목  
 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)   
 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)   
 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [위성 어셈블리 만들기](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)