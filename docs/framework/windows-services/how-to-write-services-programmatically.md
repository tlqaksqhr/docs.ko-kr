---
title: "방법: 프로그래밍 방식으로 서비스 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스, 만들기"
  - "Windows 서비스 응용 프로그램, 만들기"
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 21
---
# 방법: 프로그래밍 방식으로 서비스 작성
Windows 서비스 프로젝트 템플릿을 사용하지 않고 상속 및 다른 인프라 요소를 직접 설정하여 독자적인 서비스를 작성할 수도 있습니다.  서비스를 프로그래밍 방식으로 만들 경우 템플릿을 통해 처리할 수 있는 몇 가지 단계를 직접 수행해야 합니다.  
  
-   <xref:System.ServiceProcess.ServiceBase> 클래스에서 상속하는 서비스 클래스를 설정해야 합니다.  
  
-   서비스 프로젝트에 `Main` 메서드를 만들어 서비스가 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드를 실행하고 호출하도록 정의해야 합니다.  
  
-   <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 프로시저를 재정의하고 프로시저에서 실행할 모든 코드를 입력해야 합니다.  
  
### 프로그래밍 방식으로 서비스를 작성하려면  
  
1.  다음 단계에 따라 빈 프로젝트를 만들고 필요한 네임스페이스에 대한 참조를 만듭니다.  
  
    1.  **솔루션 탐색기**에서 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭합니다.  
  
    2.  **.NET Framework** 탭에서 **System.dll**로 스크롤한 다음 **선택**을 클릭합니다.  
  
    3.  **System.ServiceProcess.dll**로 스크롤한 다음 **선택**을 클릭합니다.  
  
    4.  **확인**을 클릭합니다.  
  
2.  클래스를 추가하고 <xref:System.ServiceProcess.ServiceBase>에서 상속하도록 구성합니다.  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  다음 코드를 추가하여 서비스 클래스를 구성합니다.  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  클래스에 대한 `Main` 메서드를 만들고 이를 사용하여 클래스에 포함될 서비스를 정의합니다. 클래스의 이름은 `userService1`입니다.  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 재정의한 다음 서비스를 시작할 때 발생시킬 모든 처리를 정의합니다.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  사용자 지정 처리로 정의할 다른 모든 메서드를 재정의한 다음 코드를 작성하여 각 경우에 서비스가 수행할 동작을 지정합니다.  
  
7.  서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다.  자세한 내용은 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)을 참조하십시오.  
  
8.  **빌드** 메뉴에서 **솔루션 빌드**를 선택하여 프로젝트를 빌드합니다.  
  
    > [!NOTE]
    >  F5 키를 눌러 프로젝트를 실행하지 마십시오. 이 방법으로는 서비스 프로젝트를 실행할 수 없습니다.  
  
9. 서비스를 설치할 사용자 지정 동작과 설치 프로젝트를 만듭니다.  예제를 보려면 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)를 참조하십시오.  
  
10. 서비스를 설치합니다.  자세한 내용은 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하십시오.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [방법: 서비스에 대한 정보 로깅](../../../docs/framework/windows-services/how-to-log-information-about-services.md)   
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)