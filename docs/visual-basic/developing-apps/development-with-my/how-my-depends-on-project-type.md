---
title: "어떻게 내 프로젝트 형식 (Visual Basic)에 따라 달라 집니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d193dade94980f04b31605ea6fa968f9fa7d0ad6
ms.lasthandoff: 03/13/2017

---
# <a name="how-my-depends-on-project-type-visual-basic"></a>My가 프로젝트 형식에 의존하는 방식(Visual Basic)
`My`특정 프로젝트 형식에 필요한 개체만 표시 합니다. 예를 들어는 `My.Forms` 개체는 Windows Forms 응용 프로그램에서 사용할 수 있지만 콘솔 응용 프로그램에서 사용할 수 없습니다. 이 항목을 설명 하는 `My` 개체를 여러 프로젝트 형식에서 사용할 수 있습니다.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>내에서 Windows 응용 프로그램 및 웹 사이트  
 `My`현재 프로젝트 형식;에 유용한 개체에만 노출 적용할 수 없는 개체를 표시 되지 않습니다. 예를 들어 다음 그림에서는 `My` Windows Forms 프로젝트의 개체 모델입니다.  
  
 ![모양의 내 Windows Forms 응용 프로그램에서](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 웹 사이트 프로젝트에서는 `My` 웹 개발자에 게 관련 된 개체를 노출 (같은 `My.Request` 및 `My.Response` 개체) 개체는 관련 없는 노출 (와 같은 `My.Forms` 개체). 다음 그림에서는 `My` 웹 사이트 프로젝트의 개체 모델:  
  
 ![모양의 내 웹 응용 프로그램에서](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>프로젝트 세부 정보  
 다음 표에 나와 있는 `My`&8; 프로젝트 형식에 대 한 개체는 기본적으로 활성화 되어 있습니다: Windows 응용 프로그램 클래스 라이브러리, 콘솔 응용 프로그램, Windows 컨트롤 라이브러리, 웹 컨트롤 라이브러리, Windows 서비스, 빈 웹 사이트, 및입니다.  
  
 다음 세 가지 버전의는 `My.Application` 개체, 두 가지 버전의는 `My.Computer` 개체 및 두 가지 버전의 `My.User` 그렇지 이러한 버전에 대 한 세부 정보는 표 뒤 각주에 제공 됩니다.  
  
|My 개체|Windows 응용 프로그램|클래스 라이브러리|콘솔 응용 프로그램|Windows 컨트롤 라이브러리|웹 컨트롤 라이브러리|Windows 서비스|Empty|웹 사이트|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Yes** <sup>1</sup>|**Yes** <sup>2</sup>|**Yes** <sup>3</sup>|**Yes** <sup>2</sup>|아니요|**Yes** <sup>3</sup>|아니요|아니요|  
|`My.Computer`|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>4</sup>|**Yes** <sup>5</sup>|**Yes** <sup>4</sup>|아니요|**Yes** <sup>5</sup>|  
|`My.Forms`|**예**|아니요|아니요|**예**|아니요|아니요|아니요|아니요|  
|`My.Log`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Request`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Resources`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.Response`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Settings`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.User`|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>6</sup>|**Yes** <sup>7</sup>|**Yes** <sup>6</sup>|아니요|**Yes** <sup>7</sup>|  
|`My.WebServices`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
  
 <sup>1</sup> Windows Forms 버전의 `My.Application`합니다. 콘솔 버전에서 파생 되며 (참고 3 참조). 응용 프로그램의 windows와 상호 작용에 대 한 지원을 추가 하 고 제공 된 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램 모델입니다.  
  
 <sup>2</sup> library의 `My.Application`합니다. 응용 프로그램에 필요한 기본 기능을 제공 합니다: 응용 프로그램 로그에 작성 하 고 응용 프로그램 정보에 액세스 하기 위한 멤버를 제공 합니다.  
  
 <sup>3</sup> 콘솔 버전의 `My.Application`합니다. 라이브러리 버전에서 파생 되며 (참고 2 참조) 하 고 응용 프로그램의 명령줄 인수 및 ClickOnce 배포 정보에 액세스 하기 위한 추가 멤버를 추가 합니다.  
  
 <sup>4</sup> Windows 버전의 `My.Computer`합니다. 서버 버전에서 파생 되며 (참고 5 참조)는 클라이언트 컴퓨터에서와 같은 키보드, 화면 및 마우스 유용한 개체에 대 한 액세스를 제공 합니다.  
  
 <sup>5</sup> 의 서버 버전 `My.Computer`합니다. 이름, 클록 등에 대 한 액세스를 같은 컴퓨터에 대 한 기본 정보를 제공합니다.  
  
 <sup>6</sup> Windows 버전의 `My.User`합니다. 이 개체는 스레드의 현재 id와 연결 됩니다.  
  
 <sup>7</sup> 웹 버전의 `My.User`합니다. 이 개체의 현재 HTTP 요청을 응용 프로그램의 사용자 id와 연결 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer></xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log></xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User></xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [사용자 지정 하는 개체는 지원 되는 내](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)
