---
title: "방법: 프로그래밍 방식으로 서비스 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 1721417b8d1fc799e6af5d09762ee852d9fbfb03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-services-programmatically"></a>방법: 프로그래밍 방식으로 서비스 작성
Windows 서비스 프로젝트 템플릿을 사용 하지 않도록 선택 상속 및 기타 인프라 요소를 설정 하 여 사용자 고유의 서비스를 작성할 수 있습니다. 서비스를 프로그래밍 방식으로 만드는 경우 서식 파일을 처리할 수 있는 몇 가지 단계를 수행 해야 합니다.  
  
-   서비스 클래스에서 상속 하도록 설정 해야는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다.  
  
-   만들어야는 `Main` 실행 되도록 서비스를 정의 하는 서비스 프로젝트 및 호출에 대 한 메서드는 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드를 합니다.  
  
-   재정의 해야 합니다는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 실행 되도록 할 절차와 모든 코드를 입력 합니다.  
  
### <a name="to-write-a-service-programmatically"></a>서비스를 프로그래밍 방식으로 작성 하려면  
  
1.  빈 프로젝트를 만들고이 단계에 따라 필요한 네임 스페이스에 대 한 참조를 만들 합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **참조** 노드와 클릭 **참조 추가**합니다.  
  
    2.  에 **.NET Framework** 탭으로 스크롤한 **System.dll** 클릭 **선택**합니다.  
  
    3.  스크롤하여 **System.ServiceProcess.dll** 클릭 **선택**합니다.  
  
    4.  **확인**을 클릭합니다.  
  
2.  클래스를 추가 하 고 구성에서 상속 하도록 <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  서비스 클래스를 구성 하려면 다음 코드를 추가 합니다.  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  만들기는 `Main` 메서드 클래스에 대 한 클래스가 포함 됩니다; 서비스를 정의 하는 데 사용 `userService1` 클래스의 이름입니다.  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  재정의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 다음 서비스를 시작할 때 발생 하는 모든 처리를 정의 합니다.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  정의 하려는 사용자 지정 처리, 다른 메서드를 재정의 하 고 각각의 경우에는 서비스가 수행할 동작을 확인 하는 코드를 작성 합니다.  
  
7.  서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
8.  선택 하 여 프로젝트를 빌드해야 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
    > [!NOTE]
    >  F5 키를 눌러 프로젝트를 실행하지 마세요. 서비스 프로젝트는 이러한 방식으로 실행할 수 없습니다.  
  
9. 설치 프로젝트 및 서비스를 설치 하려면 사용자 지정 작업을 만듭니다. 예를 들어 참조 [연습: Windows 서비스 응용 프로그램 구성 요소 디자이너에서 만드는](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)합니다.  
  
10. 서비스를 설치합니다. 자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [방법: 서비스 응용 프로그램에 설치 관리자를 추가 합니다.](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [방법: 서비스에 대 한 정보를 기록 합니다.](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [연습: 구성 요소 디자이너에는 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
