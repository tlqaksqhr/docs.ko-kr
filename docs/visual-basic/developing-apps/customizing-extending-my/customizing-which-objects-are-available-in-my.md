---
title: "My에 사용할 수 있는 개체 사용자 지정(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e5f5be7481ee102074fe1236b91110ee6b1d2944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>My에 사용할 수 있는 개체 사용자 지정(Visual Basic)
이 여기서는를 제어 하는 방법에 대해 설명 `My` 개체는 프로젝트의 설정 하 여 활성화 되어 `_MYTYPE` 조건부 컴파일 상수입니다. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 통합 개발 환경 (IDE) 유지는 `_MYTYPE` 동기화 된 프로젝트의 형식을 프로젝트에 대 한 조건부 컴파일 상수입니다.  
  
## <a name="predefined-mytype-values"></a>미리 정의 된 _MYTYPE 값  
 사용 해야 합니다는 `/define` 컴파일러 옵션을 설정 하려면는 `_MYTYPE` 조건부 컴파일 상수입니다. 에 대 한 값을 지정 하는 경우는 `_MYTYPE` 상수를 문자열 값에에서 묶어야 백슬래시/따옴표 (\\") 시퀀스입니다. 예를 들어 사용할 수 있습니다.  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 이 테이블에서는 `_MYTYPE` 몇 가지 프로젝트 형식에 대 한 조건부 컴파일 상수 설정 합니다.  
  
|프로젝트 형식|_MYTYPE 값|  
|------------------|--------------------|  
|클래스 라이브러리|"Windows"|  
|콘솔 응용 프로그램|"Console"|  
|웹|"웹"|  
|웹 컨트롤 라이브러리|"WebControl"|  
|Windows 응용 프로그램|"WindowsForms"|  
|Windows 응용 프로그램을 사용자 지정을 시작할 때`Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows 컨트롤 라이브러리|"Windows"|  
|Windows 서비스|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
>  모든 조건부 컴파일 문자열 비교는 대/소문자 구분, 방식과 관계 없이 `Option Compare` 문의 설정 합니다.  
  
## <a name="dependent-my-compilation-constants"></a>종속 _MY 컴파일 상수  
 `_MYTYPE` 조건부 컴파일 상수 값 몇 가지 다른을 차례로 제어 `_MY` 컴파일 상수:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|정의 되지 않은|"Windows"|TRUE|  
|"Custom"|정의 되지 않은|정의 되지 않은|정의 되지 않은|정의 되지 않은|정의 되지 않은|  
|"Empty"|정의 되지 않은|정의 되지 않은|정의 되지 않은|정의 되지 않은|정의 되지 않은|  
|"웹"|정의 되지 않은|"웹"|FALSE|"웹"|FALSE|  
|"WebControl"|정의 되지 않은|"웹"|FALSE|"웹"|TRUE|  
|"Windows" 또는 ""|"Windows"|"Windows"|정의 되지 않은|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 기본적으로 정의 되지 않은 조건부 컴파일 상수를 확인 `FALSE`합니다. 기본 동작을 재정의 하도록 프로젝트를 컴파일할 때 정의 되지 않은 상수에 대 한 값을 지정할 수 있습니다.  
  
> [!NOTE]
>  때 `_MYTYPE` 설정 되어 프로젝트에 포함 된 "Custom"으로 `My` 하지만 네임 스페이스에 개체가 없습니다. 그러나 설정 `_MYTYPE` 에 "빈" 컴파일러가가 추가 하지는 `My` 네임 스페이스 및 패키지 개체입니다.  
  
 이 표에서 미리 정의 된 값의 효과 `_MY` 컴파일 상수입니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|수 있도록 `My.Application`, 상수가 "콘솔 에" Windows "또는"WindowsForms":<br /><br /> -"Console" 버전에서 파생 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>합니다. 있으며 "Windows" 버전 보다 적은 수의 멤버입니다.<br />-"Windows" 버전에서 파생 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>및에 "WindowsForms" 버전 보다 적은 수의 멤버입니다.<br />-"WindowsForms" 버전의 `My.Application` 에서 파생 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>합니다. 경우는 `TARGET` 상수 "winexe" 정의 됩니다. 다음의 클래스를 포함 한 `Sub Main` 메서드.|  
|`_MYCOMPUTERTYPE`|수 있도록 `My.Computer`상수 "웹" 또는 "Windows"는 경우:<br /><br /> -"웹" 버전에서 파생 <xref:Microsoft.VisualBasic.Devices.ServerComputer>, 있으며 "Windows" 버전 보다 적은 수의 멤버입니다.<br />-의 "Windows" 버전 `My.Computer` 에서 파생 <xref:Microsoft.VisualBasic.Devices.Computer>합니다.|  
|`_MYFORMS`|수 있도록 `My.Forms`상수 있으면 `TRUE`합니다.|  
|`_MYUSERTYPE`|수 있도록 `My.User`상수 "웹" 또는 "Windows"는 경우:<br /><br /> -의 "웹" 버전 `My.User` 현재 HTTP 요청의 사용자 id와 연결 됩니다.<br />-의 "Windows" 버전 `My.User` 스레드의 현재 보안 주체와 연결 됩니다.|  
|`_MYWEBSERVICES`|수 있도록 `My.WebServices`상수 있으면 `TRUE`합니다.|  
|`_MYTYPE`|수 있도록 `My.Log`, `My.Request`, 및 `My.Response`상수 "웹"는 경우.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)
