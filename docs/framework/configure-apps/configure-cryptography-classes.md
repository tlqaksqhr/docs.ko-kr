---
title: "암호화 클래스 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework 응용 프로그램 구성, 암호화"
  - "구성 파일[.NET Framework], 암호화"
  - "암호화 알고리즘"
  - "암호화, 클래스"
  - "기본 암호화"
  - "보안[.NET Framework], 암호화"
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 암호화 클래스 구성
[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]를 사용하면 컴퓨터 관리자가 .NET Framework 및 이에 맞게 작성된 응용 프로그램에서 사용하는 기본 암호화 알고리즘 및 알고리즘 구현을 구성할 수 있습니다.  예를 들어, 자체 암호화 알고리즘 구현을 보유하고 있는 기업에서는 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]에 탑재된 알고리즘 구현 대신 해당 알고리즘 구현을 기본 암호화 알고리즘 구현으로 사용할 수 있습니다.  암호화를 사용하는 관리되는 응용 프로그램은 언제라도 명시적으로 특정 구현에 바인딩하도록 선택할 수 있지만 암호화 구성 시스템을 사용하여 암호화 개체를 생성하는 것이 좋습니다.  
  
## 단원 내용  
 [알고리즘 이름을 암호화 클래스에 매핑](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 알고리즘 이름을 암호화 클래스에 매핑하는 방법에 대해 설명합니다.  
  
 [개체 식별자를 암호화 알고리즘에 매핑](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 개체 식별자를 암호화 알고리즘에 매핑하는 방법에 대해 설명합니다.  
  
## 관련 단원  
 [암호화 서비스](../../../docs/standard/security/cryptographic-services.md)  
 [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]에서 제공하는 암호화 서비스에 대해 간단히 설명합니다.  
  
 [암호화 설정 스키마](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 암호화 알고리즘을 구현하는 클래스에 편리한 알고리즘 이름을 매핑하는 요소에 대해 설명합니다.