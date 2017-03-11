---
title: "How My Depends on Project Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "_MYTYPE"
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How My Depends on Project Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My`는 특정 프로젝트 형식에 필요한 개체만 노출합니다.  예를 들어, `My.Forms` 개체는 Windows Forms 응용 프로그램에서는 사용할 수 있지만 콘솔 응용 프로그램에서는 사용할 수 없습니다.  이 항목에서는 각 프로젝트 형식에 사용할 수 있는 `My` 개체에 대해 설명합니다.  
  
## Windows 응용 프로그램 및 웹 사이트의 My  
 `My`는 현재 프로젝트 형식에 유용한 개체만 노출하고 적용할 수 없는 개체는 노출하지 않습니다.  예를 들어, 다음 그림은 Windows Forms 프로젝트에서 `My` 개체 모델을 보여 줍니다.  
  
 ![Windows Forms 응용 프로그램의 내 모양](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 웹 사이트 프로젝트에서 `My`는 `My.Request` 및 `My.Response`와 같이 웹 개발자와 관련된 개체를 노출하고 `My.Forms` 개체와 같이 관련되지 않은 개체는 노출하지 않습니다.  다음 그림은 웹 사이트 프로젝트의 `My` 개체 모델을 보여 줍니다.  
  
 ![웹 응용 프로그램의 내 모양](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## 프로젝트 세부 사항  
 다음 표에서는 Windows 응용 프로그램, 클래스 라이브러리, 콘솔 응용 프로그램, Windows 컨트롤 라이브러리, 웹 컨트롤 라이브러리, Windows 서비스, 빈 프로젝트 및 웹 사이트라는 8가지 프로젝트 형식에서 기본적으로 사용되는 `My` 개체를 보여 줍니다.  
  
 이들 개체는 `My.Application` 개체에 세 가지 버전, `My.Computer` 개체에 두 가지 버전 그리고 `My.User` 개체에 두 가지 버전이 있습니다. 이들 버전은 표 다음에 나와 있는 각주에 자세히 설명되어 있습니다.  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|My 개체|Windows 응용 프로그램|클래스 라이브러리|콘솔 응용 프로그램|Windows 컨트롤 라이브러리|웹 컨트롤 라이브러리|Windows 서비스|비어 있음|웹 사이트|  
|`My.Application`|**예** <sup>1</sup>|**예** <sup>2</sup>|**예** <sup>3</sup>|**예** <sup>2</sup>|아니요|**예** <sup>3</sup>|아니요|아니요|  
|`My.Computer`|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>5</sup>|**예** <sup>4</sup>|아니요|**예** <sup>5</sup>|  
|`My.Forms`|**예**|아니요|아니요|**예**|아니요|아니요|아니요|아니요|  
|`My.Log`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Request`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Resources`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.Response`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Settings`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.User`|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>7</sup>|**예** <sup>6</sup>|아니요|**예** <sup>7</sup>|  
|`My.WebServices`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
  
 <sup>1</sup> `My.Application`의 Windows Forms 버전입니다.  콘솔 버전에서 파생됩니다\(참고 3 참조\). 응용 프로그램의 창과 상호 작용할 수 있도록 지원하고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 응용 프로그램 모델을 제공합니다.  
  
 <sup>2</sup> `My.Application`의 라이브러리 버전입니다.  응용 프로그램에 필요한 기본 기능을 제공합니다. 응용 프로그램 로그에 쓰고 응용 프로그램 정보에 액세스하기 위한 멤버를 제공합니다.  
  
 <sup>3</sup> `My.Application`의 콘솔 버전입니다.  라이브러리 버전에서 파생되며\(참고 2 참조\) 응용 프로그램의 명령줄 인수와 ClickOnce 배포 정보에 액세스하기 위한 추가 멤버를 제공합니다.  
  
 <sup>4</sup> `My.Computer`의 Windows 버전입니다.  서버 버전에서 파생되며\(참고 5 참조\) 클라이언트 컴퓨터에서 키보드, 화면 및 마우스 등과 같은 유용한 개체에 대한 액세스를 제공합니다.  
  
 <sup>5</sup> `My.Computer`의 서버 버전입니다.  이름, 시계 액세스 등의 컴퓨터에 관한 기본 정보를 제공합니다.  
  
 <sup>6</sup> `My.User`의 Windows 버전입니다.  이 개체는 스레드의 현재 ID와 연관됩니다.  
  
 <sup>7</sup> `My.User`의 웹 버전입니다.  이 개체는 응용 프로그램의 현재 HTTP 요청의 사용자 ID와 연관됩니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)