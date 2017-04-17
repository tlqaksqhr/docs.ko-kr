---
title: "데스크톱 응용 프로그램의 리소스 | Microsoft Docs"
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
  - "응용 프로그램 리소스"
  - "응용 프로그램 배포[.NET Framework], 리소스"
  - "지역화"
  - "리소스 지역화"
  - "응용 프로그램 리소스 패키징"
  - "리소스 파일"
  - "위성 어셈블리"
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# 데스크톱 응용 프로그램의 리소스
거의 모든 프로덕션 수준 응용 프로그램은 리소스를 사용해야 합니다.  리소스는 응용 프로그램과 함께 논리적으로 배포되는 비실행 데이터입니다.  리소스는 응용 프로그램에서 오류 메시지로 표시되거나 사용자 인터페이스의 일부로 표시될 수 있습니다.  리소스는 문자열, 이미지, 지속된 개체 등을 포함하여 수많은 형식의 데이터를 포함할 수 있습니다. 지속된 개체를 리소스 파일에 쓰려면, 해당 개체를 serialize할 수 있어야 합니다. 리소스 파일에 데이터를 저장하면 전체 응용 프로그램을 다시 컴파일하지 않고 데이터를 변경할 수 있습니다.  또한 단일 위치에 데이터를 저장할 수 있고, 여러 위치에 저장 되어 있는 하드 코드 된 데이터를 사용 하지 않아도 됩니다.  
  
 .NET Framework에서는 데스크톱 응용 프로그램에서 자원 만들기 및 지역화를 포괄적으로 지원합니다.  또한, .NET Framework는 데스크톱 응용 프로그램에서 지역화된 리소스를 패키징하고 배포하는 간단한 모델을 지원합니다.  
  
 ASP.NET 리소스에 대 한 내용은, [ASP.NET Web Page Resources Overview](../Topic/ASP.NET%20Web%20Page%20Resources%20Overview.md) Internet Explorer 개발자 센터에서 다음을 참고하십시오.  
  
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램들은 데스크톱 응용 프로그램에서 다른 리소스 모델을 사용하여 및 단일 패키지 리소스 인덱스 \(PRI\) 파일에 해당 리소스를 저장 합니다.  리소스에 대한 내용은 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램을 참조 하십시오. [Windows 스토어 앱에서 리소스를 검색하고 만들기](http://go.microsoft.com/fwlink/p/?LinkId=241674) 이것은 Windows 개발자 센터에 있습니다.  
  
## 리소스 만들기 및 지역화  
 지역화 되지 않은 응용 프로그램에 특히 소스 코드의 여러 위치에 있는 하드 코드된 문자열에 대한 응용 프로그램 데이터에 대한 리소스 파일 저장소로 사용할 수 있습니다.  가장 일반적으로, 텍스트 \(.txt\) 또는 XML \(.resx\) 파일 같은 리소스를 만들고, [Resgen.exe\(리소스 파일 생성기\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 을 사용하여 이진 .resources 파일로 컴파일할 수 있습니다.  이러한 파일은 언어 컴파일러에 의해 응용 프로그램의 실행 파일에 포함할 수 있습니다.  리소스를 만드는 자세한 내용은 다음을 참조하십시오 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).  
  
 응용 프로그램의 리소스를 특정 문화권에 맞게 지역화할 수 있습니다.  리소스를 지역화하면 지역화된\(변환된\) 버전의 응용 프로그램을 빌드할 수 있습니다.  지역화 된 리소스를 사용 하는 응용 프로그램을 개발할 때, 리소스를 사용할 수 있는 적절한 리소스가 없는 경우 사용 되는 대체 또는 중립 문화권으로 사용 되는 문화권을 지정 합니다.  일반적으로 중립 문화권의 리소스는 응용 프로그램의 실행 파일에 저장 됩니다.  각 지역화 된 문화권에 대한 나머지 리소스는 독립 실행형 위성 어셈블리에 저장 됩니다.  자세한 내용은 [위성 어셈블리 만들기](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)을 참조하십시오.  
  
## 리소스 패키징 및 배포  
 다음 위성 어셈블리에서 지역화된 응용 프로그램 리소스를 배포할 수 있습니다 [위성 어셈블리](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  위성 어셈블리는 단일 문화권의 리소스를 포함합니다. 응용 프로그램 코드는 포함 하지 않습니다.  위성 어셈블리 배포 모델에서, 하나의 기본 어셈블리 \(일반적으로 주 어셈블리\) 및 응용 프로그램에서 지원하는 각 culture에 대해 하나의 위성 어셈블리를 사용하여 응용 프로그램을 만듭니다.  위성 어셈블리는 주 어셈블리의 일부가 아니므로, 응용 프로그램의 주 어셈블리를 바꾸지 않고도 특정 문화권에 해당하는 리소스를 손쉽게 바꾸거나 업데이트할 수 있습니다.  
  
 응용 프로그램의 기본 리소스 어셈블리를 구성할 리소스를 결정할 때는 주의해야 합니다.  기본 리소스 어셈블리는 주 어셈블리의 일부이므로 이 어셈블리를 변경하려면 주 어셈블리를 바꾸어야 합니다.  기본 리소스를 제공하지 않으면 [리소스 대체 프로세스](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)에서 리소스를 찾을 때 예외가 throw됩니다.  잘 디자인된 응용 프로그램에서 리소스를 사용하면 예외가 throw되지 않습니다.  
  
 자세한 내용은 다음을 참조하십시오 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) .  
  
## 리소스 검색  
 실행 시, 응용 프로그램은 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성에 의해 지정된 문화권에 따라 적절한 지역화 된 리소스를 로드 합니다.  이 속성 값은 다음과 같이 파생됩니다:  
  
-   직접 지정하여 <xref:System.Globalization.CultureInfo> 지역화 된 문화권을 나타내는 개체는 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName> 속성입니다.  
  
-   문화권이 명시적으로 할당 되지 않은 경우에는, 다음 속성으로 부터 기본적인 스레드 UI 문화권을 가져옵니다 <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=fullName> .  
  
-   기본 스레드 UI culture가 명시적으로 할당 되지 않은 경우, 윈도우즈 `GetUserDefaultUILanguage` 함수를 호출하여 로컬 컴퓨터의 현재 사용자의 문화권을 가져옵니다.  
  
 현재 UI culture를 설정 하는 방법에 대한 자세한 내용은 참조는 <xref:System.Globalization.CultureInfo> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 페이지를 참조 합니다.  
  
 현재 UI 문화권 또는 특정 문화권의 리소스를 사용하여 검색할 수 있는 <xref:System.Resources.ResourceManager?displayProperty=fullName> 클래스입니다.  비록 <xref:System.Resources.ResourceManager> 클래스가 데스크톱 응용 프로그램에서 리소스를 검색 하는 데 가장 일반적으로 사용 되지만, <xref:System.Resources?displayProperty=fullName> 네임 스페이스는 리소스를 검색 하는 데 사용할 수 있는 추가 형식을 포함합니다.  제공합니다.  
  
-   <xref:System.Resources.ResourceReader> 클래스는 어셈블리에 포함 되거나 독립 실행형 이진.resources 파일에 저장 된 리소스를 열거할 수 있습니다.  런타임에 사용할 수 있는 리소스의 정확한 이름을 모르는 경우에 유용 합니다.  
  
-   <xref:System.Resources.ResXResourceReader> 클래스를 통해 XML \(.resx\) 파일에서 리소스를 검색할 수 있습니다.  
  
-   <xref:System.Resources.ResourceSet> 클래스를 통해 대체 규칙을 관찰 하지 않고 특정 문화권의 리소스를 검색할 수 있습니다.  리소스는 어셈블리 또는 독립 실행형 이진 .resources 파일에 저장할 수 있습니다.  다음을 개발할 수 있고 <xref:System.Resources.IResourceReader> 이 구현은 <xref:System.Resources.ResourceSet> 을 사용하여 다른 소스에서 리소스를 검색할 수 있도록 가능하세 합니다.  
  
-   <xref:System.Resources.ResXResourceSet> 클래스를 통해 메모리에 XML 리소스 파일에 있는 모든 항목을 검색할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Globalization.CultureInfo>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 [응용 프로그램 주요 사항](../../../docs/standard/application-essentials.md)   
 [리소스 파일 만들기](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [리소스 패키징 및 배포](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [위성 어셈블리 만들기](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)   
 [리소스 검색](../../../docs/framework/resources/retrieving-resources-in-desktop-apps.md)