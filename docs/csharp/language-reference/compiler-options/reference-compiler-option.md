---
title: "/reference (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/reference"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/r compiler option [C#]"
  - "reference compiler option [C#]"
  - "r compiler option [C#]"
  - "/reference compiler option [C#]"
  - "-r compiler option [C#]"
  - "metadata import [C#]"
  - "public type information [C#]"
  - "-reference compiler option [C#]"
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# /reference (C# Compiler Options)
**\/reference** 옵션을 사용하면 컴파일러에서 지정된 파일에 있는 [public](../../../csharp/language-reference/keywords/public.md) 형식 정보를 현재 프로젝트로 가져오므로 지정한 어셈블리 파일에 있는 메타데이터를 참조할 수 있습니다.  
  
## 구문  
  
```  
/reference:[alias=]filename  
/reference:filename  
```  
  
## 인수  
 `filename`  
 어셈블리 매니페스트가 들어 있는 파일의 이름을 나타냅니다.  여러 개의 파일을 가져오려면 각 파일에 대해 별도의 **\/reference** 옵션을 사용합니다.  
  
 `alias`  
 어셈블리의 모든 네임스페이스를 포함하는 루트 네임스페이스를 나타내는 유효한 C\# 식별자입니다.  
  
## 설명  
 여러 파일에서 가져오려면 각 파일에 대해 별도의 **\/reference** 옵션을 사용합니다.  
  
 가져오는 파일에는 매니페스트가 포함되어야 하며, 출력 파일은 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 이외의 [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션 중의 하나로 컴파일되어 있어야 합니다.  
  
 **\/r**는 **\/reference**의 약식 표현입니다.  
  
 어셈블리 매니페스트가 없는 출력 파일에서 메타데이터를 가져오려면 [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용합니다.  
  
 다른 어셈블리\(어셈블리 B\)를 참조하는 어셈블리\(어셈블리 A\)를 참조할 때 다음과 같은 경우에는 어셈블리 B를 참조해야 합니다.  
  
-   Assembly A에서 사용하는 형식이 Assembly B에서 상속한 형식이거나 Assembly B의 인터페이스로 구현된 경우  
  
-   Assembly B의 반환 형식이나 매개 변수 형식을 가진 필드, 속성, 이벤트 또는 메서드를 호출하는 경우  
  
 하나 이상의 어셈블리 참조가 있는 디렉터리를 지정하려면 [\/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)를 사용합니다.  **\/lib** 항목에서는 컴파일러가 어셈블리를 검색하는 디렉터리에 대해서도 설명합니다.  
  
 모듈이 아니라 어셈블리에 있는 특정 형식을 컴파일러에서 인식할 수 있도록 하려면 컴파일러에서 해당 형식을 확인할 수 있게 해야 합니다. 이를 위해 해당 형식의 인스턴스를 정의합니다.  컴파일러는 다른 방법을 사용하여 어셈블리에서 형식 이름을 확인할 수 있습니다. 예를 들어, 어셈블리에서 특정 형식을 상속하면 해당 형식 이름이 컴파일러에 전달됩니다.  
  
 경우에 따라 하나의 어셈블리 내에 있는 동일한 구성 요소의 두 가지 버전을 참조해야 할 수도 있습니다.  이렇게 하려면 각 파일에 대한 **\/reference** 스위치에 별칭 하위 옵션을 사용하여 두 파일을 구별합니다.  이 별칭은 구성 요소 이름에 대한 한정자로 사용되며 파일 중 하나에 있는 구성 요소로 확인됩니다.  
  
 일반적으로 사용되는 .NET Framework 어셈블리를 참조하는 csc 지시 파일\(.rsp\)이 기본적으로 사용됩니다.  컴파일러에 csc.rsp를 사용하지 않으려면 [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)를 사용합니다.  
  
> [!NOTE]
>  Visual Studio에서는 **참조 추가** 대화 상자를 사용합니다.  자세한 내용은 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)을 참조하십시오.  Visual Studio 2010 및 이후 버전에서는 `/reference`를 사용하고 **참조 추가** 대화 상자를 사용하여 참조를 추가하는 동작 간의 관계가 동등한지 확인합니다. 이 경우 **Embed 형식 포함** 속성은 추가 중인 어셈블리에 대해 **False**로 설정해야 합니다.  해당 속성의 기본값은 **True**입니다.  
  
## 예제  
 이 예제에서는 [extern alias](../../../csharp/language-reference/keywords/extern-alias.md) 기능을 사용하는 방법을 보여 줍니다.  
  
 소스 파일을 컴파일하고 이전에 컴파일한 `grid.dll` 및 `grid20.dll` `` 에서 메타데이터를 가져옵니다.  이러한 두 DLL에는 동일한 구성 요소의 개별 버전이 들어 있으므로 별칭 옵션과 함께 두 개의 **\/reference**를 사용하여 소스 파일을 컴파일합니다.  옵션은 다음과 같습니다.  
  
 \/reference:GridV1\=grid.dll and \/reference:GridV2\=grid20.dll  
  
 이렇게 하면 extern 문을 통해 프로그램에서 사용할 수 있는 외부 별칭 "GridV1" 및 "GridV2"가 설정됩니다.  
  
```  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 이 작업을 마치면 다음과 같이 컨트롤 이름 앞에 GridV1을 사용하여 grid.dll에 있는 grid 컨트롤을 참조할 수 있습니다.  
  
```  
GridV1::Grid  
```  
  
 또한 다음과 같이 컨트롤 이름 앞에 GridV2를 사용하여 grid20.dll에 있는 grid 컨트롤을 참조할 수도 있습니다.  
  
```  
GridV2::Grid   
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)