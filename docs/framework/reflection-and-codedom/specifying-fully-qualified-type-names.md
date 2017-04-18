---
title: "정규화된 형식 이름 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 이름"
  - "Backus-Naur 폼"
  - "BNF"
  - "정규화된 형식 이름"
  - "IDENTIFIER"
  - "언어, BNF 문법"
  - "이름[.NET Framework], 어셈블리"
  - "이름[.NET Framework], 정규화된 형식 이름"
  - "리플렉션, 정규화된 형식 이름"
  - "특수 문자"
  - "토큰"
  - "형식 이름"
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 정규화된 형식 이름 지정
다양한 리플렉션 작업에 대해 올바른 입력을 사용하려면 형식 이름을 지정해야 합니다.  정규화된 형식 이름은 어셈블리 이름 사양, 네임스페이스 사양 및 형식 이름으로 구성됩니다.  형식 이름 사양은 <xref:System.Type.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName> 및 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 같은 메서드에서 사용됩니다.  
  
## 형식 이름에 대한 BNF\(Backus\-Naur Form\) 문법  
 BNF\(Backus\-Naur Form\)는 형식 언어의 구문을 정의합니다.  다음 표에는 올바른 입력을 인식하는 방법을 설명하는 BNF 어휘 규칙이 나열되어 있습니다.  단말\(더 이상 줄일 수 없는 요소\)은 모두 대문자로 표시됩니다.  비단말\(더 줄일 수 있는 요소\)은 대\/소문자를 혼합하여 표시되거나 작은따옴표로 묶이지만, 작은따옴표\('\)는 구문 자체에 포함되지 않습니다.  파이프 기호\(&#124;\)는 하위 규칙이 있는 규칙을 나타냅니다.  
  
|정규화된 형식 이름의 BNF 문법|  
|------------------------|  
|TypeSpec                          :\=   ReferenceTypeSpec<br /><br /> &#124;     SimpleTypeSpec|  
|ReferenceTypeSpec            :\=   SimpleTypeSpec '&'|  
|SimpleTypeSpec                :\=   PointerTypeSpec<br /><br /> &#124;     ArrayTypeSpec<br /><br /> &#124;     TypeName|  
|PointerTypeSpec                :\=   SimpleTypeSpec '\*'|  
|ArrayTypeSpec                  :\=   SimpleTypeSpec '\[ReflectionDimension\]'<br /><br /> &#124;     SimpleTypeSpec '\[ReflectionEmitDimension\]'|  
|ReflectionDimension           :\=   '\*'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|ReflectionEmitDimension    :\=   '\*'<br /><br /> &#124;     Number '..' 숫자<br /><br /> &#124;     Number '…'<br /><br /> &#124;     ReflectionDimension ',' ReflectionDimension<br /><br /> &#124;     NOTOKEN|  
|Number                            :\=   \[0\-9\]\+|  
|TypeName                         :\=   NamespaceTypeName<br /><br /> &#124;     NamespaceTypeName ',' AssemblyNameSpec|  
|NamespaceTypeName        :\=   NestedTypeName<br /><br /> &#124;     NamespaceSpec '.' NestedTypeName|  
|NestedTypeName               :\=   IDENTIFIER<br /><br /> &#124;     NestedTypeName '\+' IDENTIFIER|  
|NamespaceSpec                 :\=   IDENTIFIER<br /><br /> &#124;     NamespaceSpec '.' IDENTIFIER|  
|AssemblyNameSpec           :\=   IDENTIFIER<br /><br /> &#124;     IDENTIFIER ',' AssemblyProperties|  
|AssemblyProperties            :\=   AssemblyProperty<br /><br /> &#124;     AssemblyProperties ',' AssemblyProperty|  
|AssemblyProperty              :\=   AssemblyPropertyName '\=' AssemblyPropertyValue|  
  
## 특수 문자 지정  
 형식 이름에서, IDENTIFIER는 언어 규칙에 의해 결정되는 모든 유효한 이름이 될 수 있습니다.  
  
 다음 토큰을 IDENTIFER의 일부로 사용할 때 토큰을 구분하려면 백슬래시\(\\\)를 이스케이프 문자로 사용하십시오.  
  
|토큰|의미|  
|--------|--------|  
|\\,|어셈블리 구분 기호|  
|\\\+|중첩 형식 구분 기호|  
|\\&|참조 형식|  
|\\\*|포인터 형식|  
|\\\[|배열 차원 구분 기호|  
|\\\]|배열 차원 구분 기호|  
|\\.|배열 사양에 마침표가 사용되는 경우에만 마침표 앞에 백슬래시를 사용합니다.  NamespaceSpec의 마침표에는 백슬래시가 붙지 않습니다.|  
|\\\\|문자열 리터럴로 필요한 백슬래시|  
  
 AssemblyNameSpec을 제외한 모든 TypeSpec 구성 요소에서 공백이 관련됩니다.  AssemblyNameSpec에서 ',' 구분 기호 앞에 있는 공백은 관련이 있지만 ',' 구분 기호 뒤에 있는 공백은 무시됩니다.  
  
 <xref:System.Type.FullName%2A?displayProperty=fullName> 같은 리플렉션 클래스에서는 형식 표시 이름을 반환하므로 `MyType.GetType(myType.FullName)`에서와 같이 <xref:System.Type.GetType%2A>을 호출할 때 이 반환 이름을 사용할 수 있습니다.  
  
 예를 들어, 형식의 정규화된 이름은 `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`일 수 있습니다.  
  
 네임스페이스가 `Ozzy.Out+Back`이라면 \+ 기호 앞에는 백슬래시가 있어야 합니다.  그렇지 않으면 파서에서 \+ 기호를 중첩 구분 기호로 해석합니다.  리플렉션은 이 문자열을 `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`로 내보냅니다.  
  
## 어셈블리 이름 지정  
 어셈블리 이름 사양에서 필요한 최소 정보는 어셈블리의 텍스트 이름\(IDENTIFIER\)입니다.  다음 표에 설명된 것과 같이 쉼표로 구분된 속성\/값 쌍 목록으로 이 IDENTIFIER를 만들 수 있습니다.  IDENTIFIER 명명은 파일 명명 규칙을 따라야 합니다.  IDENTIFIER에서는 대\/소문자가 구분되지 않습니다.  
  
|속성 이름|설명|허용 가능한 값|  
|-----------|--------|--------------|  
|**버전**|어셈블리 버전 번호|*Major.Minor.Build.Revision.* 여기서 *Major*, *Minor*, *Build* 및 *Revision*은 0부터 65535까지의 정수입니다.|  
|**PublicKey**|전체 공개 키|전체 공개 키의 문자열 값\(16진수 형식\).  전용 어셈블리를 명시적으로 나타내려면 null 참조\(Visual Basic의 경우 **Nothing**\)를 지정합니다.|  
|**PublicKeyToken**|공개 키 토큰\(전체 공개 키의 8바이트 해시\)|공개 키 토큰의 문자열 값\(16진수 형식\).  전용 어셈블리를 명시적으로 나타내려면 null 참조\(Visual Basic의 경우 **Nothing**\)를 지정합니다.|  
|**문화권**|어셈블리 문화권|RFC\-1766 형식의 어셈블리 문화권 또는 언어 독립\(비위성\) 어셈블리의 "중립" 문화권|  
|**사용자 지정**|사용자 지정 이진 대형 개체\(BLOB\).  이 속성은 현재 [네이티브 이미지 생성기\(Ngen\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)에서 생성된 어셈블리에만 사용됩니다.|네이티브 이미지 생성기 도구에서 설치되는 어셈블리가 네이티브 이미지이므로 네이티브 이미지 캐시에 설치된다고 어셈블리 캐시에 알릴 때 사용하는 사용자 지정 문자열.  zap 문자열이라고도 합니다.|  
  
 다음 예제에서는 기본 문화권을 사용하는 단순한 이름의 어셈블리에 대한 **AssemblyName**을 보여 줍니다.  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 다음 예제에서는 문화권 "en"을 사용하는 강력한 이름의 어셈블리에 대해 완전히 지정된 참조를 보여 줍니다.  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 다음 각 예제에서는 강력한 이름 또는 단순한 이름의 어셈블리가 만족할 수 있는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 다음 각 예제에서는 단순한 이름의 어셈블리가 만족해야 하는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 다음 각 예제에서는 강력 이름의 어셈블리가 만족해야 하는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## 포인터 지정  
 SimpleTypeSpec\*은 관리되지 않는 포인터를 나타냅니다.  예를 들어, MyType 형식에 대한 포인터를 가져오려면 `Type.GetType("MyType*")`을 사용합니다.  MyType 형식에 대한 포인터의 포인터를 가져오려면 `Type.GetType("MyType**")`을 사용합니다.  
  
## 참조 지정  
 SimpleTypeSpec & 은 관리되는 포인터나 참조를 나타냅니다.  예를 들어, MyType 형식에 대한 참조를 가져오려면 `Type.GetType("MyType &")`을 사용합니다.  포인터와 달리 참조는 수준이 하나로 제한됩니다.  
  
## 배열 지정  
 BNF 문법에서 ReflectionEmitDimension은 <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=fullName>을 사용하여 검색된 불완전한 형식 정의에만 적용됩니다.  불완전한 형식 정의는 [Reflection.Emit](frlrfSystemReflectionEmit) 를 사용하여 생성되었지만 <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=fullName> 은 아직 호출되지 않은 상태의 <xref:System.Reflection.Emit.TypeBuilder> 개체입니다.  ReflectionDimension은 완료된 모든 형식 즉, 이미 로드된 형식의 정의를 검색하는 데 사용될 수 있습니다.  
  
 배열은 다음과 같이 리플렉션에서 배열의 차수를 지정하여 액세스할 수 있습니다.  
  
-   `Type.GetType("MyArray[]")`는 하한이 0인 1차원 배열을 가져옵니다.  
  
-   `Type.GetType("MyArray[*]")`는 하한을 알 수 없는 1차원 배열을 가져옵니다.  
  
-   `Type.GetType("MyArray[][]")`는 2차원 배열의 배열을 가져옵니다.  
  
-   `Type.GetType("MyArray[*,*]")` 및 `Type.GetType("MyArray[,]")`는 하한을 알 수 없는 사각형 2차원 배열을 가져옵니다.  
  
 런타임 관점에서는 `MyArray[] != MyArray[*]`이지만 다차원 배열의 경우에는 두 표기법이 동일합니다.  즉, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")`은 **true**가 됩니다.  
  
 **ModuleBuilder.GetType**의 경우 `MyArray[0..5]`는 크기가 6이고 하한이 0인 1차원 배열을 나타냅니다.  `MyArray[4…]`는 크기를 알 수 없고 하한이 4인 1차원 배열을 나타냅니다.  
  
## 참고 항목  
 <xref:System.Reflection.AssemblyName>   
 <xref:System.Reflection.Emit.ModuleBuilder>   
 <xref:System.Reflection.Emit.TypeBuilder>   
 <xref:System.Type.FullName%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>   
 [형식 정보 보기](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)