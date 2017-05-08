---
title: "방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시 | Microsoft Docs"
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
  - "전역 어셈블리 캐시, 도구 상자 항목 선택 대화 상자"
  - "AssemblyFoldersEx, 도구 상자 항목 선택 대화 상자"
  - "컨트롤, 도구 상자 항목 선택 대화 상자에 표시"
  - "어셈블리 폴더 등록, 도구 상자 항목 선택 대화 상자"
  - "도구 상자 항목 선택 대화 상자, 컨트롤 표시"
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시
컨트롤을 개발하고 배포할 때 해당 컨트롤을 **도구 상자 항목 선택** 대화 상자에 나타나도록 할 수 있습니다. 이 대화 상자는 **도구 상자**를 마우스 오른쪽 단추로 클릭하고 **항목 선택**을 선택하면 표시되는 대화 상자입니다.  AssemblyFoldersEx 등록 절차를 사용하여 이 대화 상자에 컨트롤이 나타나도록 할 수 있습니다.  
  
### 도구 상자 항목 대화 상자에 컨트롤을 표시하려면  
  
-   전역 어셈블리 캐시에 컨트롤 어셈블리를 설치합니다.  자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)를 참조하십시오.  
  
     또는  
  
-   AssemblyFoldersEx 등록 절차를 사용하여 컨트롤 및 관련 디자인 타임 어셈블리를 등록합니다.  AssemblyFoldersEx는 타사 공급업체가 해당 공급업체에서 지원하는 각 프레임워크 버전의 경로를 저장하는 레지스트리 위치입니다.  디자인 타임 확인에서는 이 레지스트리 위치에서 참조 어셈블리를 검색합니다.  레지스트리 스크립트를 사용하여 도구 상자에 표시할 컨트롤을 지정할 수 있습니다.  자세한 내용은 [사용자 지정 컨트롤 및 디자인 타임 어셈블리 배포](http://msdn.microsoft.com/ko-kr/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)를 참조하십시오.  
  
## 참고 항목  
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [사용자 지정 컨트롤 및 디자인 타임 어셈블리 배포](http://msdn.microsoft.com/ko-kr/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)   
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)   
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)