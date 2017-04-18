---
title: "어셈블리 및 Dll의 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Dll 이름 [.NET Framework]"
  - "어셈블리 이름 [.NET Framework]"
  - "어셈블리 [.NET Framework] 이름"
  - "Dll 이름"
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 어셈블리 및 Dll의 이름
어셈블리는 배포 및 관리 코드 프로그램에 대 한 id의 단위입니다. 어셈블리에는 하나 이상의 파일 걸쳐 있을 수 있지만 일반적으로 어셈블리가 매핑됩니다 일대일 DLL로 합니다. 따라서이 섹션에서는 다음 어셈블리 명명 규칙에 매핑할 수 있는 유일한 DLL 명명 규칙을 설명 합니다.  
  
 **✓ 수행** 대량의 System.Data 등의 기능을 제안 하는 Dll 어셈블리에 대 한 이름을 선택 합니다.  
  
 DLL 이름은 네임 스페이스 이름에 해당 하지 않아도 이지만 어셈블리의 이름을 지정할 때 네임 스페이스 이름을 따르는 있습니다. 경험에의 한 어셈블리에 포함 된 어셈블리의 공통 접두사에 따라 DLL 이름을 지정 하는 것입니다. 예를 들어 두 개의 네임 스페이스를 사용 하 여 어셈블리 `MyCompany.MyTechnology.FirstFeature` 및 `MyCompany.MyTechnology.SecondFeature`, 라고 `MyCompany.MyTechnology.dll`합니다.  
  
 **✓ 고려** 다음 패턴에 따라 Dll 이름을 지정 합니다.  
  
 `<Company>.<Component>.dll`  
  
 여기서 `<Component>` 점으로 구분 된 하나 이상의 절을 포함 합니다. 예:  
  
 `Litware.Controls.dll`.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)