---
title: "인스턴스 인코딩 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 인스턴스 인코딩 옵션
SQL 워크플로 인스턴스 저장소의 **Instance Encoding Option** 속성을 사용하면 SQL 지속성 공급자가 지속성 데이터베이스에 정보를 저장하기 전에 GZip 알고리즘을 사용하여 워크플로 인스턴스 상태 정보를 압축해야 하는지 여부를 지정할 수 있습니다.이 속성에 허용되는 값은 GZip과 None입니다.기본값은 None입니다.다음 목록에서는 이러한 옵션에 대해 설명합니다.  
  
1.  **GZip**.지속성 공급자가 지속성 데이터베이스에 상태 정보를 유지하기 전에 GZip 알고리즘을 사용하여 상태 정보를 인코딩합니다.  
  
2.  **None**.지속성 공급자가 지속성 데이터베이스에 정보를 저장하기 전에 상태 정보를 인코딩하지 않습니다.  
  
 GZip을 사용하여 워크플로 인스턴스 상태 정보를 인코딩하면 SQL 데이터베이스에서 메모리 사용을 줄일 수 있으며 데이터베이스가 네트워크에서 워크플로 서비스 호스트를 실행하는 컴퓨터와 다른 컴퓨터에 상주할 경우 네트워크 사용도 줄일 수 있습니다.일반적인 지침은 워크플로 인스턴스 상태가 작은 경우 **Instance Encoding Option** 속성을 **None**으로 설정하는 것입니다.