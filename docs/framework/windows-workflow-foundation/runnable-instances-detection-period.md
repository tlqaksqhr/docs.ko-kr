---
title: "실행 가능한 인스턴스 검색 기간 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 실행 가능한 인스턴스 검색 기간
SQL 워크플로 인스턴스 저장소는 정기적으로 다시 시작되어 지속성 데이터베이스에서 실행 가능하거나 활성화 가능한 인스턴스를 검색하는 내부 태스크를 실행합니다.SQL 워크플로 인스턴스 저장소의 **Runnable Instances Detection Period** 속성은 SQL 워크플로 인스턴스 저장소에서 이전 검색 주기 이후에 검색 태스크를 실행하여 지속성 데이터베이스에서 실행 가능한 워크플로 인스턴스 또는 활성화 가능한 워크플로 인스턴스를 검색하는 기간을 지정합니다.  
  
 이 속성의 간격을 짧게 설정할수록 워크플로 인스턴스와 연결된 타이머 만료 시간과 인스턴스 이벤트 및 후속 로드 신호 사이의 간격이 줄어듭니다.하지만 호스트의 처리 부하가 증가하므로 지속적인 타이머 및\/또는 호스트 오류가 거의 없는 시나리오에서는 유용하지 않을 수 있습니다.속성 형식은 TimeSpan이고 속성 값은 hh:mm:ss 형식을 따릅니다.이 속성의 최소값은 00:00:01이고기본값은 00:00:05입니다.  
  
 실행 및 활성화 가능한 워크플로 인스턴스를 검색하여 활성화하는 방법은 [인스턴스 활성화](../../../docs/framework/windows-workflow-foundation//instance-activation.md)를 참조하십시오.