---
title: "Customizing Which Objects are Available in My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Customizing Which Objects are Available in My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 프로젝트의 `_MYTYPE` 조건부 컴파일 상수를 설정하여 활성화할 `My` 개체를 제어하는 방법을 설명합니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] IDE\(통합 개발 환경\)에서는 프로젝트의 `_MYTYPE` 조건부 컴파일 상수를 프로젝트의 형식과 동기화하여 유지합니다.  
  
## 미리 정의된 \_MYTYPE 값  
 `_MYTYPE` 조건부 컴파일 상수를 설정하려면 `/define` 컴파일 옵션을 사용해야 합니다.  `_MYTYPE` 상수에 대한 값을 직접 지정할 때는 문자열 값 앞뒤에 백슬래시\/따옴표\(\\"\) 시퀀스를 붙여야 합니다.  예를 들면, 다음을 사용할 수 있습니다.  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 이 표에서는 몇 가지 프로젝트 형식에 설정되는 `_MYTYPE` 조건부 컴파일 상수를 보여 줍니다.  
  
|프로젝트 형식|\_MYTYPE 값|  
|-------------|----------------|  
|클래스 라이브러리|"Windows"|  
|콘솔 응용 프로그램|"Console"|  
|웹|"Web"|  
|웹 컨트롤 라이브러리|"WebControl"|  
|Windows 응용 프로그램|"WindowsForms"|  
|Windows 응용 프로그램, 사용자 지정 `Sub Main`으로 시작하는 경우|"WindowsFormsWithCustomSubMain"|  
|Windows 컨트롤 라이브러리|"Windows"|  
|Windows 서비스|"Console"|  
|비어 있음|"Empty"|  
  
> [!NOTE]
>  모든 조건부 컴파일 문자열 비교에서는 `Option Compare` 문의 설정 방식에 관계없이 대\/소문자를 구분합니다.  
  
## 독립적 \_MY 컴파일 상수  
 `_MYTYPE` 조건부 컴파일 상수는 다음과 같은 몇 개의 다른 `_MY` 컴파일 상수 값을 차례로 제어합니다.  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|정의되어 있지 않습니다.|"Windows"|TRUE|  
|"Custom"|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|  
|"Empty"|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|정의되어 있지 않습니다.|  
|"Web"|정의되어 있지 않습니다.|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|정의되어 있지 않습니다.|"Web"|FALSE|"Web"|TRUE|  
|"Windows" 또는 ""|"Windows"|"Windows"|정의되어 있지 않습니다.|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 기본적으로 정의되지 않은 조건부 컴파일 상수는 `FALSE`로 확인됩니다.  프로젝트를 컴파일할 때 정의되지 않은 상수에 대한 값을 지정하여 기본 동작을 재정의할 수 있습니다.  
  
> [!NOTE]
>  `_MYTYPE`을 "Custom"으로 설정하면 프로젝트에는 `My` 네임스페이스가 포함되지만 개체는 포함되지 않습니다.  하지만 `_MYTYPE`을 "Empty"로 설정하면 컴파일러에서 `My` 네임스페이스와 개체를 추가하지 않습니다.  
  
 이 표에서는 `_MY` 컴파일 상수의 미리 정의된 값이 미치는 효과를 설명합니다.  
  
|상수|의미|  
|--------|--------|  
|`_MYAPPLICATIONTYPE`|상수가 "Console," Windows" 또는 "WindowsForms"인 경우 `My.Application`을 활성화합니다.<br /><br /> -   "Console" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>에서 파생되며  "Windows" 버전보다 멤버 수가 적습니다.<br />-   "Windows" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>에서 파생되며 "WindowsForms" 버전보다 멤버 수가 적습니다.<br />-   `My.Application`의 "WindowsForms" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>에서 파생됩니다.  `TARGET` 상수를 "winexe"로 정의하면 클래스에 `Sub Main` 메서드가 포함됩니다.|  
|`_MYCOMPUTERTYPE`|상수가 "Web" 또는 "Windows"인 경우 `My.Computer`를 활성화합니다.<br /><br /> -   "Web" 버전은 <xref:Microsoft.VisualBasic.Devices.ServerComputer>에서 파생되며 "Windows" 버전보다 멤버 수가 적습니다.<br />-   `My.Computer`의 "Windows" 버전은 <xref:Microsoft.VisualBasic.Devices.Computer>에서 파생됩니다.|  
|`_MYFORMS`|상수가 `TRUE`인 경우 `My.Forms`을 활성화합니다.|  
|`_MYUSERTYPE`|상수가 "Web" 또는 "Windows"인 경우 `My.User`를 활성화합니다.<br /><br /> -   `My.User`의 "Web" 버전은 현재 HTTP 요청의 사용자 ID와 연관됩니다.<br />-   `My.User`의 "Windows" 버전은 스레드의 현재 principal과 연관됩니다.|  
|`_MYWEBSERVICES`|상수가 `TRUE`인 경우 `My.WebServices`을 활성화합니다.|  
|`_MYTYPE`|상수가 "Web"인 경우 `My.Log`, `My.Request` 및 `My.Response`를 활성화합니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)