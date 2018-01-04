---
title: "방법: Windows 서비스 계속(Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 73b16a5e5834f7279ae551d4e7efd26cc86c1d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>방법: Windows 서비스 계속(Visual Basic)
사용 하 여이 예제는 <xref:System.ServiceProcess.ServiceController> 로컬 컴퓨터에서 IIS 관리 서비스를 계속 하려면 구성 요소입니다.  
  
## <a name="example"></a>예  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다. 에 있는 코드 조각 선택에서 **Windows 운영 체제 > Windows 서비스**합니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.serviceprocess.dll에 대 한 프로젝트 참조 합니다.  
  
-   <xref:System.ServiceProcess> 네임스페이스의 멤버에 대한 액세스 권한. 코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 의 속성은 <xref:System.ServiceProcess.ServiceController> 클래스는 기본적으로 로컬 컴퓨터입니다. 다른 컴퓨터에서 Windows 서비스를 참조 하려면 변경 된 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성을 해당 컴퓨터의 이름입니다.  
  
 호출할 수 없습니다는 <xref:System.ServiceProcess.ServiceController.Continue%2A> 서비스 컨트롤러 상태가 될 때까지 서비스의 메서드입니다 <xref:System.ServiceProcess.ServiceControllerStatus.Paused>합니다.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   서비스를 다시 시작할 수 없습니다. (<xref:System.InvalidOperationException>)  
  
-   시스템 API에 액세스할 때 오류가 발생했습니다. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 컴퓨터에서 서비스의 제어를 사용 하 여 제한 될 수도 있습니다는 <xref:System.ServiceProcess.ServiceControllerPermissionAccess> 사용 권한을 설정 하는 열거형은 <xref:System.ServiceProcess.ServiceControllerPermission> 클래스입니다.  
  
 사용 하 여 서비스 정보에 대 한 액세스를 제한할 수 있습니다는 <xref:System.Security.Permissions.PermissionState> 사용 권한을 설정 하는 열거형은 <xref:System.Security.Permissions.SecurityPermission> 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [방법: Windows 서비스 일시 중지(Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
