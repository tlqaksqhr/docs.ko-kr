---
title: "방법: 설치된 .NET Framework 업데이트 확인"
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
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba734dd3a9585b52b96cb2d27743da6190961126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a>방법: 설치된 .NET Framework 업데이트 확인
컴퓨터에 설치된 각 .NET Framework 버전에 대해 설치된 업데이트는 Windows 레지스트리에 나열됩니다. 레지스트리 편집기(regedit.exe)를 사용하여 이 정보를 볼 수 있습니다.  
  
 레지스트리 편집기에서 .NET Framework 버전과 각 버전에 대해 설치된 업데이트는 서로 다른 하위 키에 저장되어 있습니다. 설치된 버전 번호 검색에 대한 자세한 내용은 [방법: 설치된 .NET Framework 버전 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조하세요. .NET Framework 설치에 대한 자세한 내용은 [개발자용 .NET Framework 설치](../../../docs/framework/install/guide-for-developers.md)를 참조하세요.  
  
### <a name="to-find-installed-updates"></a>설치된 업데이트를 찾으려면  
  
1.  **regedit.exe** 프로그램을 엽니다. Windows 8 이상에서는 시작 화면을 열고 이름을 입력합니다. 이전 버전의 Windows에서는 **시작** 메뉴에서 **실행**을 선택하고 **열기** 상자에 **regedit.exe**를 입력합니다.  
  
     regedit.exe를 실행하려면 관리자 자격 증명이 있어야 합니다.  
  
2.  레지스트리 편집기에서 다음 하위 키를 엽니다.  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates  
  
     설치된 업데이트가 적용되는 .NET Framework 버전을 식별하는 하위 키 아래에 나열됩니다. 각 업데이트는 KB(기술 자료) 번호로 식별됩니다.  
  
## <a name="example"></a>예제  
 다음 코드는 컴퓨터에 설치된 .NET Framework 업데이트를 프로그래밍 방식으로 확인합니다. 이 예제를 실행하려면 관리자 자격 증명이 있어야 합니다.  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)]
 [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 이 예제는 다음과 유사한 출력 결과를 표시합니다.  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a>참고 항목

[방법: 설치된 .NET Framework 버전 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)   
[.NET Framework 설치](../../../docs/framework/install/guide-for-developers.md)   
[버전 및 종속성](../../../docs/framework/migration-guide/versions-and-dependencies.md)
