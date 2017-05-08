---
title: "Blittable 형식 및 비 Blittable 형식 | Microsoft Docs"
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
  - "blittable 형식, interop 마샬링"
  - "interop 마샬링, blittable 형식"
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Blittable 형식 및 비 Blittable 형식
대부분의 데이터 형식에는 관리되는 메모리와 관리되지 않는 메모리 모두에서 공통되는 표현이 있으므로, interop 마샬러에서 특별한 처리를 하지 않아도 됩니다.  이러한 형식은 관리 코드와 비관리 코드 사이에서 전달될 때 변환할 필요가 없으므로 *blittable 형식*이라고 합니다.  
  
 플랫폼 호출로부터 반환되는 구조체는 blittable 형식이어야 합니다.  플랫폼 호출에서는 반환 형식으로 비 blittable 구조체가 지원되지 않습니다.  
  
 <xref:System> 네임스페이스에 있는 다음 형식은 blittable 형식입니다.  
  
-   <xref:System.Byte?displayProperty=fullName>  
  
-   <xref:System.SByte?displayProperty=fullName>  
  
-   <xref:System.Int16?displayProperty=fullName>  
  
-   <xref:System.UInt16?displayProperty=fullName>  
  
-   <xref:System.Int32?displayProperty=fullName>  
  
-   <xref:System.UInt32?displayProperty=fullName>  
  
-   <xref:System.Int64?displayProperty=fullName>  
  
-   <xref:System.UInt64?displayProperty=fullName>  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Single?displayProperty=fullName>  
  
-   <xref:System.Double?displayProperty=fullName>  
  
 다음의 복잡한 형식도 blittable 형식입니다.  
  
-   blittable 형식의 1차원 배열\(예: 정수 배열\).  그러나 blittable 형식의 가변 배열이 들어 있는 형식은 blittable 형식이 아닙니다.  
  
-   일반적으로는 blittable 형식만 포함하고, 특별히 formatted 형식으로 마샬링된 경우에는 클래스도 포함하는 formatted 값 형식.  formatted 값 형식에 대한 자세한 내용은 [Default Marshaling for Value Types](http://msdn.microsoft.com/ko-kr/4d9a876c-e05a-40ba-bd85-bd22877f984a)을 참조하십시오.  
  
 개체 참조는 blittable 형식이 아닙니다.  여기에는 자체적으로 blittable 형식인 개체에 대한 참조 배열이 포함됩니다.  예를 들어, blittable 형식의 구조체를 정의할 수 있지만 이러한 구조체에 대한 참조 배열이 들어 있는 blittable 형식은 정의할 수 없습니다.  
  
 최적화 방법으로 blittable 멤버만 포함된 blittable 형식 및 클래스의 배열은 마샬링하는 동안 복사되는 대신 [고정](../../../docs/framework/interop/copying-and-pinning.md)됩니다.  이러한 형식은 호출자와 호출 수신자가 동일한 아파트에 있을 때 In\/Out 매개 변수로 마샬링되는 것처럼 보일 수 있습니다.  그러나 실제로 이러한 형식은 In 매개 변수로 마샬링되며, 인수를 In\/Out 매개 변수로 마샬링하려면 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 적용해야 합니다.  
  
 일부 관리되는 데이터 형식은 관리되지 않은 환경에서 서로 다른 표현을 필요로 합니다.  이러한 비 blittable 데이터 형식은 마샬링될 수 있는 형식으로 변환되어야 합니다.  예를 들어 관리되는 문자열은 마샬링되기 전에 문자열 개체로 변환되어야 하므로 비 blittable 형식입니다.  
  
 다음 표에서는 <xref:System> 네임스페이스에 있는 비 blittable 형식을 보여 줍니다.  정적 메서드 또는 클래스 인스턴스를 참조하는 데이터 구조체인 [대리자](http://msdn.microsoft.com/ko-kr/d176ee76-f982-494b-b03d-92e4118896e2)도 비 blittable 형식입니다.  
  
|비 blittable 형식|설명|  
|--------------------|--------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C 스타일 배열 또는 `SAFEARRAY`로 변환됩니다.|  
|[System.Boolean](http://msdn.microsoft.com/ko-kr/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|`true`가 1 또는 \-1로 표시되는 1, 2 또는 4바이트 값으로 변환됩니다.|  
|[System.Char](http://msdn.microsoft.com/ko-kr/cecc87c1-075e-4cde-aa56-33d189f66feb)|유니코드 또는 ANSI 문자로 변환됩니다.|  
|[System.Class](http://msdn.microsoft.com/ko-kr/fe334af5-0123-43d8-be84-26f6f023ddb6)|클래스 인터페이스로 변환됩니다.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|variant 또는 인터페이스로 변환됩니다.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C 스타일 배열 또는 `SAFEARRAY`로 변환됩니다.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|null 참조에서 종료되는 문자열 또는 BSTR로 변환됩니다.|  
|[System.Valuetype](http://msdn.microsoft.com/ko-kr/4d9a876c-e05a-40ba-bd85-bd22877f984a)|메모리 레이아웃이 고정된 구조체로 변환됩니다.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C 스타일 배열 또는 `SAFEARRAY`로 변환됩니다.|  
  
 클래스 및 개체 형식은 COM interop에서만 지원됩니다.  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# 및 C\+\+에서의 이러한 형식을 보려면 [클래스 라이브러리 개요](../../../docs/standard/class-library-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [기본 마샬링 동작](../../../docs/framework/interop/default-marshaling-behavior.md)