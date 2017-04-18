---
title: "Windows Forms 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "액세스 제어, Windows Forms"
  - "디자이너 액세스 보안"
  - "권한, Windows Forms"
  - "보안[Windows Forms]"
  - "보안 정책, Windows Forms"
  - "Windows Forms, 보안"
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Forms 보안
Windows Forms에는 코드를 기반으로 하는 보안 모델 기능이 있습니다. 이 때 보안 수준은 코드에 대해 설정되며 해당 코드를 실행하는 사용자와는 상관이 없습니다.  이 기능은 컴퓨터에 이미 사용되고 있는 보안 스키마에 추가적으로 사용됩니다.  이 기능은 브라우저에서 사용할 수 있는 보안 기능\(예: Internet Explorer에서 사용할 수 있는 영역 기반 보안\)이나 운영 체제에 있는 보안 기능\(예: Windows NT의 자격 증명 기반 보안\)을 포함할 수 있습니다.  
  
## 단원 내용  
 [Windows Forms의 보안 개요](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 .NET Framework 보안 모델과 응용 프로그램에서 Windows Forms의 보안을 유지하는 데 필요한 기본 단계를 간단히 설명합니다.  
  
 [Windows Forms의 파일 및 데이터 액세스 추가 보안](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 부분 신뢰 환경에서 파일 및 데이터에 액세스하는 방법을 설명합니다.  
  
 [Windows Forms의 인쇄 추가 보안](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 부분 신뢰 환경에서 인쇄 기능에 액세스하는 방법을 설명합니다.  
  
 [Windows Forms의 추가 보안 고려 사항](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 부분 신뢰 환경에서 창 조작, 클립보드 사용, 비관리 코드 호출 등의 작업을 수행하는 방법을 설명합니다.  
  
## 관련 단원  
 [NIB: Default Security Policy](http://msdn.microsoft.com/ko-kr/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 완전 신뢰, 로컬 인트라넷 및 인터넷 사용 권한 집합에서 부여되는 기본 사용 권한을 나열합니다.  
  
 [NIB: General Security Policy Administration](http://msdn.microsoft.com/ko-kr/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 .NET Framework 보안 정책 관리와 사용 권한 높이기에 대해 설명합니다.  
  
 [위험한 권한 및 정책 관리](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 잠재적으로 보안 시스템에 우회하여 침입하는 데 사용될 수 있는 일부 .NET Framework 사용 권한에 대해 설명합니다.  
  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)  
 .NET Framework에 대해 안전하게 코드를 작성할 수 있는 최상의 방법을 설명하는 항목으로 안내합니다.  
  
 [NIB: Requesting Permissions](http://msdn.microsoft.com/ko-kr/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 코드 실행에 필요한 사용 권한을 런타임에 알려 주는 특성을 사용하는 방법을 설명합니다.  
  
 [주요 보안 개념](../../../docs/standard/security/key-security-concepts.md)  
 코드 보안의 기본 사항을 다루는 항목으로 안내합니다.  
  
 [코드 액세스 보안 기본 사항](../../../docs/framework/misc/code-access-security-basics.md)  
 .NET Framework 런타임 보안 정책을 사용하여 작업하는 기본적인 방법에 대해 설명합니다.  
  
 [NIB: Determining When to Modify Security Policy](http://msdn.microsoft.com/ko-kr/af749b17-e461-409d-84b9-a3d44789db16)  
 응용 프로그램에 대한 기본 보안 정책을 바꿀 시기를 결정하는 방법을 설명합니다.  
  
 [NIB: Deploying Security Policy](http://msdn.microsoft.com/ko-kr/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 보안 정책 변경 사항을 배포하는 최상의 방법을 설명합니다.