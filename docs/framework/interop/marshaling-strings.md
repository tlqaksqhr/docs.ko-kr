---
title: "문자열 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링, 플랫폼 호출"
  - "데이터 마샬링, 샘플"
  - "데이터 마샬링, 문자열"
  - "마샬링, 플랫폼 호출"
  - "마샬링, 샘플"
  - "마샬링. 문자열"
  - "플랫폼 호출, 데이터 마샬링"
  - "샘플 응용 프로그램[.NET Framework], 문자열 마샬링"
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 문자열 마샬링
플랫폼 호출에서는 필요하면 문자열 매개 변수를 .NET Framework 형식인 유니코드에서 관리되지 않는 형식인 ANSI로 변환하여 복사합니다.  관리되는 문자열은 변경할 수 없으므로 플랫폼 호출에서는 함수 반환 시 관리되지 않는 메모리에서 관리되는 메모리로 문자열을 다시 복사하지 않습니다.  
  
 다음 표에서는 문자열의 마샬링 옵션을 보여 주고 각 옵션의 용도에 대해 설명한 다음 해당되는 .NET Framework 샘플의 링크를 제공합니다.  
  
|String|설명|샘플|  
|------------|--------|--------|  
|값으로|문자열을 In 매개 변수를 통해 전달합니다.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|결과로|비관리 코드에서 문자열을 반환합니다.|[문자열](http://msdn.microsoft.com/ko-kr/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|참조로|<xref:System.Text.StringBuilder>를 사용하여 문자열을 In\/Out 매개 변수를 통해 전달합니다.|[Buffers](http://msdn.microsoft.com/ko-kr/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|구조체에서 값으로|In 매개 변수인 구조체에서 문자열을 전달합니다.|[Structs](http://msdn.microsoft.com/ko-kr/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|구조체에서 참조로**\(char\*\)**|In\/Out 매개 변수인 구조체에서 문자열을 전달합니다.  관리되지 않는 함수에서는 문자 버퍼에 대한 포인터를 필요로 하며 버퍼 크기는 구조체의 멤버입니다.|[문자열](http://msdn.microsoft.com/ko-kr/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|구조체에서 참조로**\(char\[\]\)**|In\/Out 매개 변수인 구조체에서 문자열을 전달합니다.  관리되지 않는 함수에서는 포함된 문자 버퍼를 필요로 합니다.|[OSInfo](http://msdn.microsoft.com/ko-kr/69d89067-507b-41fe-859d-30bf3ff29455)|  
|클래스에서 값으로**\(char\*\)**|클래스에서 문자열을 전달합니다. 클래스는 In\/Out 매개 변수입니다.  관리되지 않는 함수에서는 문자 버퍼에 대한 포인터를 필요로 합니다.|[OpenFileDlg](http://msdn.microsoft.com/ko-kr/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|클래스에서 값으로**\(char\[\]\)**|클래스에서 문자열을 전달합니다. 클래스는 In\/Out 매개 변수입니다.  관리되지 않는 함수에서는 포함된 문자 버퍼를 필요로 합니다.|[OSInfo](http://msdn.microsoft.com/ko-kr/69d89067-507b-41fe-859d-30bf3ff29455)|  
|문자열 배열로서 값으로|값으로 전달되는 문자열 배열을 만듭니다.|[배열](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|문자열이 포함된 구조체 배열로서 값으로|문자열을 포함하는 구조체 배열을 만들며 이 배열이 값으로 전달됩니다.|[배열](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## 참고 항목  
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ko-kr/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [클래스, 구조체 및 공용 구조체 마샬링](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshaling Arrays of Types](http://msdn.microsoft.com/ko-kr/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/ko-kr/a915c948-54e9-4d0f-a525-95a77fd8ed70)