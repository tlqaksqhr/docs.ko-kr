---
title: "/moduleassemblyname (C# Compiler Option) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/moduleassemblyname"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "moduleassemblyname compiler option [C#]"
  - "/moduleassemblyname compiler option [C#]"
  - ".moduleassemblyname compiler option [C#]"
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# /moduleassemblyname (C# Compiler Option)
netmodule에서 액세스할 수 있는 public이 아닌 형식으로 된 어셈블리를 지정합니다.  
  
## 구문  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## 인수  
 `assembly_name`  
 public이 아닌 형식이 .netmodule을 입력하는 어셈블리의 이름에 액세스 할 수 있습니다.  
  
## 설명  
 **\/moduleassemblyname** 는 .netmodule를 빌드하는 경우와 다음과 같은 경우에 사용 되어야 합니다:  
  
-   netmodule은 기존 어셈블리의 public이 아닌 형식에 액세스해야 합니다.  
  
-   .netmodule를 빌드할 어셈블리의 이름을 알아야 합니다.  
  
-   존재하는 어셈블리는 .netmodule를 빌드할 어셈블리에 대해 friend 어셈블리 액세스를 허용합니다.  
  
 .netmodule를 빌드할 자세한 내용은 다음을 참조하십시오. [\/target:module \(Create Module to Add to Assembly\)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 이 옵션은 개발 환경 내에서 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
## 예제  
 이 샘플에서는 csman\_an\_assembly라는 어셈블리에 friend 어셈블리 액세스를 제공하는 private 형식의 어셈블리를 빌드합니다.  
  
```  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## 예제  
 이 예제는 moduleassemblyname\_1.dll 어셈블리의 public이 아닌 형식에 액세스하는 .netmodule를 빌드합니다.  이 .Netmodule이 csman\_an\_assembly 라는 어셈블리로 빌드 되는지를 알면, 우리는 csman\_an\_assembly에 대한 friend 어셈블리 액세스 권한이 부여 된 어셈블리에서 public이 아닌 형식에 액세스 할 수 있도록 **\/moduleassemblyname**를 지정할 수 있습니다.  
  
```  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## 예제  
 이 코드 샘플에서는 이전에 빌드한 어셈블리와 .netmodule을 참조하여 csman\_an\_assembly 어셈블리를 빌드합니다.  
  
```  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
  **An\_Internal\_Class.Test 호출됨**   
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)