---
title: "방법: Windows 서비스 일시 중지(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController.Pause"
helpviewer_keywords: 
  - "Windows 서비스 응용 프로그램 일시 중지"
  - "Windows 서비스 응용 프로그램, 일시 중지"
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# 방법: Windows 서비스 일시 중지(Visual Basic)
이 예제에서는 <xref:System.ServiceProcess.ServiceController> 구성 요소를 사용하여 로컬 컴퓨터에서 IIS 관리자 서비스를 일시 중지합니다.  
  
## 예제  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **Windows 운영 체제 \> Windows 서비스**에 있습니다.  자세한 내용은 [코드 조각](../Topic/Code%20Snippets.md)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.serviceprocess.dll에 대한 프로젝트 참조  
  
-   <xref:System.ServiceProcess> 네임스페이스의 멤버에 대한 액세스 권한.  코드에서 멤버 이름을 정규화하지 않는 경우에는 `Imports` 문을 추가합니다.  자세한 내용은 [Imports Statement \(.NET Namespace and Type\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하십시오.  
  
## 강력한 프로그래밍  
 <xref:System.ServiceProcess.ServiceController> 클래스의 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성은 기본적으로 로컬 컴퓨터로 설정됩니다.  다른 컴퓨터에서 Windows 서비스를 참조하려면 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성을 해당 컴퓨터의 이름으로 변경합니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   서비스를 일시 중지할 수 없는 경우  \([InvalidOperationException 클래스](frlrfSystemInvalidOperationExceptionClassTopic)\)  
  
-   시스템 API에 액세스하는 도중 오류가 발생한 경우  \([Win32Exception 클래스](frlrfSystemComponentModelWin32ExceptionClassTopic)\)  
  
## .NET Framework 보안  
 [ServiceControllerPermissionAccess 열거형](frlrfSystemServiceProcessServiceControllerPermissionAccessClassTopic)을 사용하여 [ServiceControllerPermission 클래스](frlrfSystemServiceProcessServiceControllerPermissionClassTopic)의 권한을 설정하면 컴퓨터에서 서비스에 대한 제어를 제한할 수 있습니다.  
  
 [PermissionState 열거형](frlrfSystemSecurityPermissionsPermissionStateClassTopic)을 사용하여 [SecurityPermission 클래스](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic)의 권한을 설정하면 서비스 정보에 대한 액세스를 제한할 수 있습니다.  
  
## 참고 항목  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>   
 [방법: Windows 서비스 계속\(Visual Basic\)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)