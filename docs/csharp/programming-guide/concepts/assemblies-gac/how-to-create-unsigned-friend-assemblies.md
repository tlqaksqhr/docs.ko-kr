---
title: "방법: 서명되지 않은 Friend 어셈블리 만들기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 854df39394ef10bf2404fb3f762586fb102fba7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a>방법: 서명되지 않은 Friend 어셈블리 만들기(C#)
이 예제에서는 서명되지 않은 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>어셈블리 및 friend 어셈블리를 만들려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  다음 코드가 포함된 `friend_signed_A.`라는 C# 파일을 만듭니다. 코드에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 friend_signed_B를 friend 어셈블리로 선언합니다.  
  
    ```csharp  
    // friend_unsigned_A.cs  
    // Compile with:   
    // csc /target:library friend_unsigned_A.cs  
    using System.Runtime.CompilerServices;  
    using System;  
  
    [assembly: InternalsVisibleTo("friend_unsigned_B")]  
  
    // Type is internal by default.  
    class Class1  
    {  
        public void Test()  
        {  
            Console.WriteLine("Class1.Test");  
        }  
    }  
  
    // Public type with internal member.  
    public class Class2  
    {  
        internal void Test()  
        {  
            Console.WriteLine("Class2.Test");  
        }  
    }  
    ```  
  
3.  다음 명령을 사용하여 friend_signed_A를 컴파일하고 서명합니다.  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4.  다음 코드가 포함된 `friend_unsigned_B`라는 C# 파일을 만듭니다. friend_unsigned_A는 friend_unsigned_B를 friend 어셈블리로 지정하기 때문에 friend_unsigned_B의 코드는 friend_unsigned_A의 `internal` 형식과 멤버에 액세스할 수 있습니다.  
  
    ```csharp  
    // friend_unsigned_B.cs  
    // Compile with:   
    // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            // Access an internal type.  
            Class1 inst1 = new Class1();  
            inst1.Test();  
  
            Class2 inst2 = new Class2();  
            // Access an internal member of a public type.  
            inst2.Test();  
  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
5.  다음 명령을 사용하여 friend_signed_B를 컴파일합니다.  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다. `/out` 컴파일러 옵션을 사용하여 출력 어셈블리(.exe 또는 .dll)의 이름을 명시적으로 지정해야 합니다. 자세한 내용은 [/out(C# 컴파일러 옵션)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)을 참조하세요.  
  
6.  friend_signed_B.exe 파일을 실행합니다.  
  
     프로그램이 두 문자열 "Class1.Test" 및 "Class2.Test"를 인쇄합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다. 주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `internal` 형식 및 멤버의 표시 유형을 제어한다는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [어셈블리 및 전역 어셈블리 캐시(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [Friend 어셈블리 (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [방법: 서명 된 Friend 어셈블리 (C#) 만들기](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)
