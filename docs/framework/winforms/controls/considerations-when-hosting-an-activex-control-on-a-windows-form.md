---
title: "Windows Form에서 ActiveX 컨트롤을 호스팅할 때 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ActiveX 컨트롤[Windows Forms], 추가"
  - "ActiveX 컨트롤[Windows Forms], 호스팅"
  - "Windows Forms 컨트롤, ActiveX 컨트롤"
  - "Windows Forms, ActiveX 컨트롤"
  - "Windows Forms, ActiveX 컨트롤 호스팅"
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Windows Form에서 ActiveX 컨트롤을 호스팅할 때 고려 사항
Windows Forms은 Windows Forms 컨트롤을 호스팅하기에 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다.  다음은 ActiveX 컨트롤을 사용하는 응용 프로그램을 작성할 때 유의해야 할 사항입니다.  
  
-   **보안** 공용 언어 런타임이 코드 액세스 보안 측면에서 강화되었습니다.  Windows Forms 기능이 있는 응용 프로그램은 문제 없이 완전히 신뢰할 수 있는 환경에서 실행할 수 있고 대부분의 기능에 액세스할 수 있는 부분적으로 신뢰할 수 있는 환경에서도 실행할 수 있습니다.  Windows Forms 컨트롤은 브라우저에서 아무 문제 없이 호스팅될 수 있지만  Windows Forms의 ActiveX 컨트롤은 이러한 향상된 보안 기능을 활용할 수 없습니다.  ActiveX 컨트롤을 실행하려면 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=fullName> 속성으로 설정하는 비관리 코드 권한이 필요합니다.  보안 및 비관리 코드 권한에 대한 자세한 내용은 [SecurityPermissionAttribute 클래스](frlrfSystemSecurityPermissionsSecurityPermissionAttributeClassTopic)를 참조하십시오.  
  
-   **TCO\(전체 소유 비용\)** Windows Form에 추가된 ActiveX 컨트롤은 Windows Form과 함께 전부 배포되므로 파일의 크기가 상당히 커질 수 있습니다.  또한 Windows Forms에서 ActiveX 컨트롤을 사용하려면 레지스트리에 기록해야 합니다.  따라서 레지스트리에 기록할 필요가 없는 Windows Forms 컨트롤을 사용하는 것에 비해 사용자의 컴퓨터를 간섭할 여지가 많습니다.  
  
    > [!NOTE]
    >  ActiveX 컨트롤로 작업하려면 COM Interop 래퍼를 사용해야 합니다.  자세한 내용은 [Visual Basic 및 Visual C\#에서 COM 상호 운용성](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)을 참조하십시오.  
  
    > [!NOTE]
    >  ActiveX 컨트롤 멤버의 이름이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 정의된 이름과 일치하면 ActiveX 컨트롤 가져오기는 <xref:System.Windows.Forms.AxHost> 파생 클래스를 만들 때 멤버 이름 앞에 **Ctl**을 붙입니다.  예를 들어 ActiveX 컨트롤의 **Layout**이라는 멤버는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 내에 **Layout** 이벤트가 정의되어 있는 경우 해당 멤버의 이름이 AxHost 파생 클래스에서 **CtlLayout**으로 변경됩니다.  
  
## 참고 항목  
 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [코드 액세스 보안](../../../../docs/framework/misc/code-access-security.md)   
 [Controls and Programmable Objects Compared in Various Languages and Libraries](http://msdn.microsoft.com/ko-kr/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)