---
title: "Serialization 바인더 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Serialization 바인더 사용
이 샘플에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 사용하여 제네릭 형식이 serialize될 때 이 형식의 버전을 변경하는 방법을 보여 줍니다.  
  
## 세부 항목  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## 추가 설명  
 이 샘플에서는 서로 다른 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]를 대상으로 하는 두 엔터티가 이진 포맷터와 serialization 바인더를 사용하여 통신하는 방법을 보여 줍니다.  
  
 이 샘플은 .NET Remoting을 사용하여 개발되었습니다.이 샘플은 제네릭 형식으로 계약을 구현하는 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 대상의 서버와 두 개의 서로 다른 클라이언트로 구성되어 있습니다. 두 클라이언트는 각각 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] 및 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]을 대상으로 합니다.  
  
 서버에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 이진 포맷터에 연결하여 serialization 시 형식 버전을 적절하게 변경할 수 있도록 하므로 두 클라이언트 모두 해당 형식을 올바르게 deserialize할 수 있습니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  클라이언트를 실행하려면 SBGenericsVTS 솔루션\(6개의 프로젝트\)을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.  
  
2.  **공용 속성**에서 **시작 프로젝트**를 선택하고 **여러 개의 시작 프로젝트**를 선택합니다.  
  
3.  먼저 **Server**를 선택하고 **Client20**을 선택한 다음 **Client40**을 선택합니다.이 세 프로젝트에 대한 **시작** 동작을 선택하고 나머지 설정은 **없음**으로 둡니다.  
  
4.  **확인**을 클릭하고 F5 키를 눌러 샘플을 실행합니다.