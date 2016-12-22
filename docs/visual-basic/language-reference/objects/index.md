---
title: "Objects (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "objects [Visual Basic]"
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 항목에는 Visual Basic 런타임 개체를 설명하는 다른 항목에 대한 링크와 해당 멤버 프로시저, 속성 및 이벤트의 표가 포함되어 있습니다.  
  
## Visual Basic 런타임 개체  
  
|||  
|-|-|  
|<xref:Microsoft.VisualBasic.Collection>|편리하게 관련 항목 그룹을 단일 개체로 참조할 수 있습니다.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|런타임 오류에 대한 정보를 포함합니다.|  
|`My.Application` 개체는 다음 클래스로 구성됩니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>는 모든 프로젝트에서 사용할 수 있는 멤버를 제공합니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 메서드는 Windows Forms 응용 프로그램에서 사용할 수 있는 멤버를 제공합니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> 메서드는 콘솔 응용 프로그램에서 사용할 수 있는 멤버를 제공합니다.|현재 응용 프로그램이나 DLL과 연결된 데이터만 제공됩니다.  시스템 수준 정보는 `My.Application`으로 변경할 수 없습니다.<br /><br /> 일부 멤버는 Windows Forms 또는 콘솔 응용 프로그램에서만 사용할 수 있습니다.|  
|`My.Application.Info` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>\)|버전 번호, 설명, 로드된 어셈블리 등의 응용 프로그램에 대한 정보를 가져오기 위한 속성을 제공합니다.|  
|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|응용 프로그램의 로그 수신기에 이벤트 및 예외 정보를 쓸 수 있는 속성 및 메서드를 제공합니다.|  
|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|오디오, 시계, 키보드, 파일 시스템 등과 같은 컴퓨터 구성 요소를 조작하기 위한 속성을 제공합니다.|  
|`My.Computer.Audio` \(<xref:Microsoft.VisualBasic.Devices.Audio>\)|소리 재생을 위한 메서드를 제공합니다.|  
|`My.Computer.Clipboard` \(<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>\)|클립보드 조작을 위한 메서드를 제공합니다.|  
|`My.Computer.Clock` \(<xref:Microsoft.VisualBasic.Devices.Clock>\)|시스템 시계에서 현재 현지 시간과 지역 표준시\(그리니치 표준시라고도 함\)에 액세스하기 위한 속성을 제공합니다.|  
|`My.Computer.FileSystem` \(<xref:Microsoft.VisualBasic.FileIO.FileSystem>\)|드라이브, 파일 및 디렉터리 관련 작업을 수행하기 위한 속성과 메서드를 제공합니다.|  
|`My.Computer.FileSystem.SpecialDirectories` \(<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>\)|주로 참조되는 디렉터리에 액세스하기 위한 속성을 제공합니다.|  
|`My.Computer.Info` \(<xref:Microsoft.VisualBasic.Devices.ComputerInfo>\)|컴퓨터의 메모리, 로드된 어셈블리, 이름 및 운영 체제에 대한 정보를 가져오기 위한 속성을 제공합니다.|  
|`My.Computer.Keyboard` \(<xref:Microsoft.VisualBasic.Devices.Keyboard>\)|현재 눌러져 있는 키와 같은 키보드의 현재 상태에 액세스하기 위한 속성을 제공하고 활성 창에 키 입력을 보내기 위한 메서드를 제공합니다.|  
|`My.Computer.Mouse` \(<xref:Microsoft.VisualBasic.Devices.Mouse>\)|로컬 컴퓨터에 설치된 마우스의 형식과 구성에 대한 정보를 가져오기 위한 속성을 제공합니다.|  
|`My.Computer.Network` \(<xref:Microsoft.VisualBasic.Devices.Network>\)|컴퓨터가 연결되는 네트워크와 상호 작용하기 위한 속성, 이벤트 및 메서드를 제공합니다.|  
|`My.Computer.Ports` \(<xref:Microsoft.VisualBasic.Devices.Ports>\)|컴퓨터의 직렬 포트에 액세스하기 위한 속성과 메서드를 제공합니다.|  
|`My.Computer.Registry` \(<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>\)|레지스트리 조작을 위한 속성과 메서드를 제공합니다.|  
|[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)|현재 프로젝트에 선언된 각 Windows Form의 인스턴스에 액세스하기 위한 속성을 제공합니다.|  
|`My.Log` \(<xref:Microsoft.VisualBasic.Logging.AspLog>\)|웹 응용 프로그램에 대한 응용 프로그램의 로그 수신기에 이벤트 및 예외 정보를 쓰기 위한 속성과 메서드를 제공합니다.|  
|[My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)|요청된 페이지의 <xref:System.Web.HttpRequest> 개체를 가져옵니다.  `My.Request` 개체에는 현재 HTTP 요청 정보가 포함되어 있습니다.<br /><br /> `My.Request` 개체는 [!INCLUDE[vstecasp](../../../visual-basic/developing-apps/programming/drives-directories-files/includes/vstecasp_md.md)] 응용 프로그램에만 사용할 수 있습니다.|  
|[My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md)|응용 프로그램의 리소스에 액세스하기 위한 속성과 클래스를 제공합니다.|  
|[My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)|<xref:System.Web.UI.Page>와 연결된 <xref:System.Web.HttpResponse> 개체를 가져옵니다.  이 개체를 사용하면 클라이언트에 HTTP 응답 데이터를 보내고 이 응답에 대한 정보를 포함할 수 있습니다.<br /><br /> `My.Response` 개체는 [!INCLUDE[vstecasp](../../../visual-basic/developing-apps/programming/drives-directories-files/includes/vstecasp_md.md)] 응용 프로그램에만 사용할 수 있습니다.|  
|[My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)|응용 프로그램의 설정에 액세스하기 위한 속성과 메서드를 제공합니다.|  
|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|현재 사용자에 대한 정보에 액세스할 수 있도록 합니다.|  
|[My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)|현재 프로젝트에서 참조하는 각 웹 서비스의 단일 인스턴스를 만들고 액세스하기 위한 속성을 제공합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|구조화된 텍스트 파일을 구문 분석하기 위한 메서드와 속성을 제공합니다.|  
  
## 참고 항목  
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../../visual-basic/index.md)