---
title: "Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e35679245d93a98b76bff31d97c6111146348a00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항
Windows Forms는 Windows Forms 컨트롤을 호스팅하도록 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다. ActiveX 컨트롤을 사용하는 응용 프로그램을 계획할 때 다음 사항을 고려하세요.  
  
-   **보안** 공용 언어 런타임이 코드 액세스 보안과 관련하여 향상되었습니다. Windows Forms 기능이 있는 응용 프로그램은 완전히 신뢰할 수 있는 환경에서 문제 없이 실행할 수 있으며, 대부분의 기능에 액세스할 수 있지만 부분적으로 신뢰할 수 있는 환경에서도 실행할 수 있습니다. Windows Forms 컨트롤은 브라우저에서 별다른 어려움 없이 간단하게 호스팅될 수 있지만, Windows Forms의 ActiveX 컨트롤은 향상된 보안 기능을 사용할 수 없습니다. 으로 설정 된 비관리 코드 권한이 ActiveX 컨트롤을 실행 하려면는 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> 속성입니다. 보안 및 비관리 코드 권한이 대 한 자세한 내용은 참조 <xref:System.Security.Permissions.SecurityPermissionAttribute>합니다.  
  
-   **TCO(총 소유 비용)** Windows Form에 추가된 ActiveX 컨트롤은 해당 Windows Form과 함께 전부 배포되므로 만들어지는 파일의 크기가 상당히 커질 수 있습니다. 또한 Windows Forms에서 ActiveX 컨트롤을 사용하려면 레지스트리에 기록해야 합니다. 이 작업은 레지스트리에 기록할 필요가 없는 Windows Forms 컨트롤에 비해 사용자의 컴퓨터를 간섭할 여지가 많습니다.  
  
    > [!NOTE]
    >  ActiveX 컨트롤을 사용하려면 COM interop 래퍼를 사용해야 합니다. 자세한 내용은 [Visual Basic 및 Visual C#의 COM 상호 운용성](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하세요.  
  
    > [!NOTE]
    >  ActiveX 컨트롤의 멤버의 이름에 정의 된 이름과 일치 하는 경우는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], ActiveX 컨트롤 가져오기를 사용 하 여 멤버 이름을 접두사는 다음 **Ctl** 를 만들 때의 <xref:System.Windows.Forms.AxHost> 클래스를 파생 합니다. 예를 들어 ActiveX 컨트롤에 **Layout**이라는 멤버가 있으면 **Layout** 이벤트가 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 이미 정의되어 있으므로 AxHost 파생 클래스에서 이 멤버의 이름이 **CtlLayout**으로 변경됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [코드 액세스 보안](../../../../docs/framework/misc/code-access-security.md)  
 [여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)
