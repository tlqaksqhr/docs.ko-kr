---
title: "MsgBox 샘플 | Microsoft Docs"
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
  - "데이터 마샬링, MsgBox 샘플"
  - "마샬링, MsgBox 샘플"
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# MsgBox 샘플
이 샘플에서는 문자열 형식을 In 매개 변수를 통해 값으로 전달하는 방법과 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 및 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> 필드의 사용 시기를 보여 줍니다.  
  
 MsgBox 샘플에서는 다음의 관리되지 않는 함수를 사용합니다. 이 함수는 원래의 함수 선언과 함께 표시되어 있습니다.  
  
-   User32.dll에서 내보낸 **MessageBox**  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 이 샘플에서, `LibWrap` 클래스에는 `MsgBoxSample` 클래스에서 호출하는 각각의 관리되지 않는 함수에 대한 관리되는 프로토타입이 포함되어 있습니다.  관리되는 프로토타입 메서드인 `MsgBox`, `MsgBox2` 및 `MsgBox3`에서는 동일한 관리되지 않는 함수에 대한 선언이 서로 다릅니다.  
  
 `MsgBox2`에 대한 선언에서는 ANSI로 지정된 문자 형식이 유니코드 함수의 이름인 진입점 `MessageBoxW`와 일치하지 않으므로 올바르지 않은 출력이 생성됩니다.  `MsgBox3`에 대한 선언에서는 **EntryPoint**, **CharSet** 및 **ExactSpelling** 필드 간에 불일치가 발생됩니다.  `MsgBox3`을 호출하면 예외가 throw됩니다.  문자열 명명 및 이름 마샬링에 대한 자세한 내용은 [문자 집합 지정](../../../docs/framework/interop/specifying-a-character-set.md)을 참조하십시오.  
  
## 프로토타입 선언  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## 함수 호출  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## 참고 항목  
 [문자열 마샬링](../../../docs/framework/interop/marshaling-strings.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ko-kr/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [문자열에 대한 기본 마샬링](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md)