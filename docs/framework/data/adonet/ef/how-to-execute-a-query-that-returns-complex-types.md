---
title: "방법: 복합 형식을 반환하는 쿼리 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 복합 형식을 반환하는 쿼리 실행
이 항목에서는 복합 형식의 속성이 포함된 엔터티 형식 개체를 반환하는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.  
  
### 이 예제의 코드를 실행하려면  
  
1.  프로젝트에 [AdventureWorks Sales Model](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832)을 추가하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  .edmx 파일을 두 번 클릭하여 Entity Designer의 [모델 브라우저 창](http://msdn.microsoft.com/ko-kr/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd)에 모델을 표시합니다.  Entity Designer 화면에서 `Contact` 엔터티 형식의 `Email` 및 `Phone` 속성을 선택한 다음 마우스 오른쪽 단추를 클릭하고 **새 복합 형식으로 리팩터링**을 선택합니다.  
  
4.  선택한 `Email` 및 `Phone` 속성이 포함된 새 복합 형식이 **모델 브라우저**에 추가됩니다.  복합 형식에 기본 이름이 지정됩니다. **속성** 창에서 형식의 이름을 `EmailPhone`으로 바꿉니다.  또한 새 `ComplexProperty` 속성이 `Contact` 엔터티 형식에 추가됩니다.  속성의 이름을 으로 바꿉니다.  
  
     엔터티 데이터 모델 마법사를 사용하여 복합 형식을 만들고 수정하는 방법에 대한 자세한 내용은 [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/ko-kr/5b2eb3b3-693d-42cb-b43a-405812d677eb) 및 [How to: Create and Modify Complex Types](http://msdn.microsoft.com/ko-kr/afb8e206-0ffe-4597-b6d4-6ab566897e1d)을 참조하세요.  
  
## 예제  
 다음 예제에서는 `Contact` 개체의 컬렉션을 반환하고 `Contact` 개체의 두 속성인 `ContactID` 및 `EmailPhoneComplexType` 복합 형식의 값을 표시하는 쿼리를 실행합니다.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]