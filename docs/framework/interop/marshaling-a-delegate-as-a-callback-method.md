---
title: "콜백 메서드로 대리자 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링, Callback 샘플"
  - "마샬링, Callback 샘플"
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 콜백 메서드로 대리자 마샬링
이 샘플에서는 함수 포인터를 필요로 하는 관리되지 않는 함수에 대리자를 전달하는 방법을 보여 줍니다.  대리자는 메서드에 대한 참조를 보유할 수 있으며 형식 안전 함수 포인터 또는 콜백 함수와 같은 클래스입니다.  
  
> [!NOTE]
>  호출 내에서 대리자를 사용하는 경우 공용 언어 런타임에서는 호출하는 동안 해당 대리자가 가비지 수집되지 않도록 보호합니다.  그러나 관리되지 않는 함수에서 호출 완료 후 사용할 대리자를 저장하는 경우에는 관리되지 않는 함수에서 대리자 사용을 마칠 때까지 사용자가 직접 가비지 수집을 방지해야 합니다.  자세한 내용은 [HandleRef 샘플](http://msdn.microsoft.com/ko-kr/ab23b04e-1d53-4ec7-b27a-e892d9298959) 및 [GCHandle 샘플](http://msdn.microsoft.com/ko-kr/6acce798-0385-4ded-a790-77da842c113f)을 참조하십시오.  
  
 Callback 샘플에서는 다음의 관리되지 않는 함수를 사용합니다. 이 함수들은 원래의 함수 선언과 함께 표시되어 있습니다.  
  
-   PinvokeLib.dll에서 내보낸 **TestCallBack**  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   PinvokeLib.dll에서 내보낸 **TestCallBack2**  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/ko-kr/5d1438d7-9946-489d-8ede-6c694a08f614)은 이러한 함수에 대한 구현이 포함된, 관리되지 않는 사용자 지정 라이브러리입니다.  
  
 이 샘플에서, `LibWrap` 클래스에는 `TestCallBack` 및 `TestCallBack2` 메서드에 대한 관리되는 프로토타입이 포함되어 있습니다.  두 메서드 모두 콜백 함수에 대리자를 매개 변수로 전달합니다.  대리자의 시그니처는 해당 대리자가 참조하는 메서드의 시그니처와 일치해야 합니다.  예를 들어, `FPtr` 및 `FPtr2` 대리자에는 `DoSomething` 및 `DoSomething2` 메서드와 동일한 시그니처가 있습니다.  
  
## 프로토타입 선언  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## 함수 호출  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## 참고 항목  
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/ko-kr/a915c948-54e9-4d0f-a525-95a77fd8ed70)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ko-kr/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)