---
title: "동일 형식 및 포함된 Interop 형식 | Microsoft Docs"
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
  - "포함된 interop 형식"
  - "NoPIA"
  - "주 Interop 어셈블리, CLR 버전 4에서 필요하지 않음"
  - "형식 동등성"
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# 동일 형식 및 포함된 Interop 형식
[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 이후부터는 공용 언어 런타임에서 COM 형식에 대한 형식 정보를 관리되는 어셈블리에 직접 포함할 수 있게 지원하며, 관리되는 어셈블리에게 COM 형식에 대한 형식 정보를 interop 어셈블리에서 가져오도록 요구하지 않습니다.  포함된 형식 정보에는 관리되는 어셈블리에서 실제로 사용하는 형식과 멤버만 포함되기 때문에 관리되는 두 어셈블리는 동일한 COM 형식에 대해 매우 다른 뷰를 가질 수도 있습니다.  관리되는 각 어셈블리는 COM 형식에 대한 자체적인 뷰를 나타내기 위해 서로 다른 <xref:System.Type> 개체를 가집니다.  공용 언어 런타임에서는 인터페이스, 구조체, 열거형 및 대리자별로 서로 다른 뷰 간의 동일 형식을 지원합니다.  
  
 동일 형식이란 관리되는 특정 어셈블리에서 다른 어셈블리로 전달되는 COM 개체가 수신 어셈블리에서 적절한 관리되는 형식으로 캐스팅될 수 있음을 의미합니다.  
  
> [!NOTE]
>  동일 형식 및 포함된 interop 형식의 경우 interop 어셈블리를 응용 프로그램과 함께 배포할 필요가 없기 때문에 COM 구성 요소를 사용하는 응용 프로그램 및 추가 기능의 배포가 단순화됩니다.  그러나 공유 COM 구성 요소가 이전 버전의 .NET Framework에서도 사용되도록 하려는 개발자는 PIA\(주 interop 어셈블리\)를 만들어야 합니다.  
  
## 동일 형식  
 COM 형식 일치는 인터페이스, 구조체, 열거형 및 대리자에 대해 지원됩니다.  다음 조건이 모두 충족될 경우 COM 형식은 서로 동일합니다.  
  
-   두 형식 모두 인터페이스이거나 구조체, 열거형 또는 대리자입니다.  
  
-   형식의 ID가 서로 동일합니다. 이에 대한 설명은 다음 단원에서 제공됩니다.  
  
-   두 형식 모두 동일 형식의 자격을 가집니다. 이에 대한 설명은 [COM 형식을 동일 형식으로 표시](#type_equiv) 단원에서 제공됩니다.  
  
### 형식 ID  
 두 형식의 범위 및 ID가 일치할 경우, 즉 두 형식에 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 각각 있고 두 특성의 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 및 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 속성이 일치할 경우 두 형식은 ID가 서로 동일한 것으로 간주됩니다.  <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 비교 시 대\/소문자는 구분되지 않습니다.  
  
 형식에 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 없거나 범위 및 식별자를 지정하지 않은 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 있는 경우 형식의 동일성 여부는 다음과 같이 판단할 수 있습니다.  
  
-   인터페이스의 경우 <xref:System.Runtime.InteropServices.GuidAttribute>의 값이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=fullName> 속성 대신 사용되고, <xref:System.Type.FullName%2A?displayProperty=fullName> 속성\(네임스페이스를 포함하는 형식 이름\)이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=fullName> 속성 대신 사용됩니다.  
  
-   구조체, 열거형 및 대리자의 경우 포함 어셈블리의 <xref:System.Runtime.InteropServices.GuidAttribute>가 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 대신 사용되고, <xref:System.Type.FullName%2A?displayProperty=fullName> 속성이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 속성 대신 사용됩니다.  
  
<a name="type_equiv"></a>   
### COM 형식을 동일 형식으로 표시  
 동일 형식의 자격이 있는 것으로 형식을 표시하는 방법은 다음 두 가지가 있습니다.  
  
-   <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성을 형식에 적용합니다.  
  
-   형식을 COM 가져오기 형식으로 표시합니다.  인터페이스에 <xref:System.Runtime.InteropServices.ComImportAttribute> 특성이 있는 경우 인터페이스는 COM 가져오기 형식입니다.  정의되어 있는 어셈블리에 <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> 특성이 있는 경우 인터페이스, 구조체, 열거형 또는 대리자는 COM 가져오기 형식입니다.  
  
## 참고 항목  
 <xref:System.Type.IsEquivalentTo%2A>   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)