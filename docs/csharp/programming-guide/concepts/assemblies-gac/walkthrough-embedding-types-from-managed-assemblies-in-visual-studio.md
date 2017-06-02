---
title: "연습: Visual Studio에서 관리되는 어셈블리의 형식 포함(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 3bb7e2c9665cf98fe48e1445dfcf8009b329a39a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a>연습: Visual Studio에서 관리되는 어셈블리의 형식 포함(C#)
강력한 이름의 관리되는 어셈블리에서 형식 정보를 포함하는 경우 응용 프로그램에서 유형을 느슨하게 연결하여 버전 독립성을 확보할 수 있습니다. 즉, 각 버전에 대해 컴파일하지 않고도 관리되는 라이브러리의 여러 버전에서 형식을 사용하도록 프로그램을 작성할 수 있습니다.  
  
 형식 포함은 Microsoft Office의 자동화 개체를 사용하는 응용 프로그램과 같은 COM interop에서 자주 사용됩니다. 형식 정보를 포함하면 서로 다른 컴퓨터의 서로 다른 Microsoft Office 버전에서 동일한 빌드의 프로그램을 작동할 수 있습니다. 그러나 완전하게 관리되는 솔루션에서도 형식 포함을 사용할 수 있습니다.  
  
 다음과 같은 특징이 있는 어셈블리에서 형식 정보를 포함할 수 있습니다.  
  
-   어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.  
  
-   포함된 인터페이스는 `ComImport` 특성 및 `Guid` 특성(그리고 고유한 GUID)으로 주석이 추가됩니다.  
  
-   어셈블리는 `ImportedFromTypeLib` 특성이나 `PrimaryInteropAssembly` 특성, 그리고 어셈블리 수준의 `Guid` 특성으로 주석이 추가됩니다. 기본적으로 Visual C# 프로젝트 템플릿에는 어셈블리 수준의 `Guid` 특성이 포함됩니다.  
  
 포함할 수 있는 공용 인터페이스를 지정한 후에 이러한 인터페이스를 구현하는 런타임 클래스를 만들 수 있습니다. 그런 다음 클라이언트 프로그램은 공용 인터페이스가 포함된 어셈블리를 참조하고 참조의 `Embed Interop Types` 속성을 `True`로 설정하여 디자인 타임에 해당 인터페이스의 형식 정보를 포함할 수 있습니다. 이는 명령줄 컴파일러를 사용하고 `/link` 컴파일러 옵션을 사용하여 어셈블리를 참조하는 것과 같습니다. 그러면 클라이언트 프로그램은 해당 인터페이스로 형식이 지정된 런타임 개체의 인스턴스를 로드할 수 있습니다. 강력한 이름의 런타임 어셈블리의 새 버전을 만들면 업데이트된 런타임 어셈블리로 클라이언트 프로그램을 다시 컴파일할 필요가 없습니다. 대신, 클라이언트 프로그램은 공용 인터페이스에 대해 포함된 형식 정보를 통해 사용 가능한 런타임 어셈블리 버전을 계속 사용합니다.  
  
 형식 포함의 기본 기능은 COM interop 어셈블리에서 형식 정보를 포함하도록 지원하는 것이므로, 완전히 관리되는 솔루션에 형식 정보를 포함할 때 다음과 같은 제한 사항이 적용됩니다.  
  
-   COM interop 관련 특성만 포함되고 다른 특성은 무시됩니다.  
  
-   형식이 제네릭 매개 변수를 사용하고 제네릭 매개 변수의 형식이 포함된 형식인 경우 해당 형식을 어셈블리 경계에서 사용할 수 없습니다. 어셈블리 경계를 넘어가는 예로는 다른 어셈블리에서 메서드를 호출하는 경우 또는 다른 어셈블리에 정의된 형식에서 형식이 파생되는 경우를 들 수 있습니다.  
  
-   상수는 포함되지 않습니다.  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 클래스는 포함된 형식을 키로 지원하지 않습니다. 포함된 형식을 키로서 지원하도록 고유한 사전 형식을 구현할 수 있습니다.  
  
 이 연습에서는 다음을 수행합니다.  
  
-   포함할 수 있는 형식 정보가 있는 공개 인터페이스와 함께 강력한 이름의 어셈블리를 만듭니다.  
  
-   해당 공용 인터페이스를 구현하는 강력한 이름의 런타임 어셈블리를 만듭니다.  
  
-   공용 인터페이스에서 형식 정보를 포함하고 런타임 어셈블리에서 클래스의 인스턴스를 만드는 클라이언트 프로그램을 만듭니다.  
  
-   런타임 어셈블리를 수정하고 다시 빌드합니다.  
  
-   클라이언트 프로그램을 실행하여, 클라이언트 프로그램을 다시 컴파일할 필요 없이 런타임 어셈블리의 새 버전이 사용되고 있는지 확인합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a>인터페이스 만들기  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>동등한 형식의 인터페이스 프로젝트를 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **클래스 라이브러리**를 선택합니다. **이름** 상자에 `TypeEquivalenceInterface`을 입력한 다음 **확인**을 클릭합니다. 새 프로젝트가 만들어집니다.  
  
3.  **솔루션 탐색기**에서 Class1.cs 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다. 파일 이름을 `ISampleInterface.cs`로 바꾸고 ENTER 키를 누릅니다. 파일 이름을 바꾸면 클래스 이름도 `ISampleInterface`로 바뀝니다. 이 클래스는 클래스에 대한 공용 인터페이스를 나타냅니다.  
  
4.  TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **빌드** 탭을 클릭합니다. 개발 컴퓨터의 유효한 위치(예: `C:\TypeEquivalenceSample`)로 출력 경로를 설정합니다. 이 연습의 이후 단계에서도 이 위치가 사용됩니다.  
  
5.  프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다. **어셈블리 서명** 옵션을 선택합니다. **강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다. **키 파일 이름** 상자에 `key.snk`를 입력합니다. **암호로 내 키 파일 보호** 확인란의 선택을 취소합니다. **확인**을 클릭합니다.  
  
6.  ISampleInterface.cs 파일을 엽니다. ISampleInterface 인터페이스를 만드는 ISampleInterface 클래스 파일에 다음 코드를 추가합니다.  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  **도구** 메뉴에서 **GUID 만들기**를 클릭합니다. **GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다. **끝내기**를 클릭합니다.  
  
8.  `Guid` 특성에서 샘플 GUID를 삭제하고, **GUID 만들기** 대화 상자에서 복사한 GUID를 붙여 넣습니다. 복사된 GUID에서 중괄호({})를 제거합니다.  
  
9. **솔루션 탐색기**에서 **Properties** 폴더를 확장합니다. AssemblyInfo.cs 파일을 두 번 클릭합니다. 파일에 다음 특성을 추가합니다.  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     파일을 저장합니다.  
  
10. 프로젝트를 저장합니다.  
  
11. TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다. 클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).  
  
## <a name="creating-a-runtime-class"></a>런타임 클래스 만들기  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>동등한 형식의 런타임 프로젝트를 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **클래스 라이브러리**를 선택합니다. **이름** 상자에 `TypeEquivalenceRuntime`을 입력한 다음 **확인**을 클릭합니다. 새 프로젝트가 만들어집니다.  
  
3.  **솔루션 탐색기**에서 Class1.cs 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다. 파일 이름을 `SampleClass.cs`로 바꾸고 ENTER 키를 누릅니다. 파일 이름을 바꾸면 클래스 이름도 `SampleClass`로 바뀝니다. 이 클래스는 `ISampleInterface` 인터페이스를 구현합니다.  
  
4.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **빌드** 탭을 클릭합니다. TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).  
  
5.  프로젝트 속성을 편집하는 동안 **서명** 탭을 클릭합니다. **어셈블리 서명** 옵션을 선택합니다. **강력한 이름 키 파일 선택** 목록에서 **<새로 만들기...>**를 클릭합니다. **키 파일 이름** 상자에 `key.snk`를 입력합니다. **암호로 내 키 파일 보호** 확인란의 선택을 취소합니다. **확인**을 클릭합니다.  
  
6.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다. **찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다. TypeEquivalenceInterface.dll 파일을 선택하고 **확인**을 클릭합니다.  
  
7.  **솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다. TypeEquivalenceInterface 참조를 선택합니다. TypeEquivalenceInterface 참조에 대한 속성 창에서 **특정 버전** 속성을 **False**로 설정합니다.  
  
8.  다음 코드를 SampleClass 클래스 파일에 추가하여 SampleClass 클래스를 만듭니다.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. 프로젝트를 저장합니다.  
  
10. TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다. 클래스 라이브러리 .dll 파일이 컴파일되고 지정된 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).  
  
## <a name="creating-a-client-project"></a>클라이언트 프로젝트 만들기  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>동등한 형식의 클라이언트 프로젝트를 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다. **이름** 상자에 `TypeEquivalenceClient`를 입력한 다음 **확인**을 클릭합니다. 새 프로젝트가 만들어집니다.  
  
3.  TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **빌드** 탭을 클릭합니다. TypeEquivalenceInterface 프로젝트에서 사용한 것과 같은 위치로 출력 경로를 설정합니다(예: `C:\TypeEquivalenceSample`).  
  
4.  TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다. **찾아보기** 탭을 클릭하여 출력 경로 폴더로 이동합니다. TypeEquivalenceInterface.dll 파일(TypeEquivalenceRuntime.dll 아님)을 선택하고 **확인**을 클릭합니다.  
  
5.  **솔루션 탐색기**를 확장하고 **References** 폴더를 확장합니다. TypeEquivalenceInterface 참조를 선택합니다. TypeEquivalenceInterface 참조에 대한 속성 창에서 **Interop 형식 포함** 속성을 **True**로 설정합니다.  
  
6.  다음 코드를 Program.cs 파일에 추가하여 클라이언트 프로그램을 만듭니다.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  Ctrl+F5를 눌러 프로그램을 빌드하고 실행합니다.  
  
## <a name="modifying-the-interface"></a>인터페이스 수정  
  
#### <a name="to-modify-the-interface"></a>인터페이스를 수정하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.  
  
2.  **프로젝트 열기** 대화 상자에서 TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **응용 프로그램** 탭을 클릭합니다. **어셈블리 정보** 단추를 클릭합니다. **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.  
  
3.  SampleInterface.cs 파일을 엽니다. ISampleInterface 인터페이스에 다음 코드 줄을 추가합니다.  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     파일을 저장합니다.  
  
4.  프로젝트를 저장합니다.  
  
5.  TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다. 클래스 라이브러리 .dll 파일의 새 버전이 컴파일되고 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).  
  
## <a name="modifying-the-runtime-class"></a>런타임 클래스 수정  
  
#### <a name="to-modify-the-runtime-class"></a>런타임 클래스를 수정하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **열기**를 가리킨 다음 **프로젝트/솔루션**을 클릭합니다.  
  
2.  **프로젝트 열기** 대화 상자에서 TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **응용 프로그램** 탭을 클릭합니다. **어셈블리 정보** 단추를 클릭합니다. **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`으로 변경합니다.  
  
3.  SampleClass.cs 파일을 엽니다. SampleClass 클래스에 다음 코드 줄을 추가합니다.  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     파일을 저장합니다.  
  
4.  프로젝트를 저장합니다.  
  
5.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다. 클래스 라이브러리 .dll 파일의 업데이트된 버전이 컴파일되고 앞서 지정한 빌드 출력 경로에 저장됩니다(예: C:\TypeEquivalenceSample).  
  
6.  파일 탐색기에서 출력 경로 폴더를 엽니다(예: C:\TypeEquivalenceSample). TypeEquivalenceClient.exe를 두 번 클릭하여 프로그램을 실행합니다. 다시 컴파일하지 않고도 이 프로그램은 TypeEquivalenceRuntime 어셈블리의 새 버전을 반영합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/link(C# 컴파일러 옵션)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)   
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)   
 [어셈블리를 사용한 프로그래밍](../../../../framework/app-domains/programming-with-assemblies.md)   
 [어셈블리 및 전역 어셈블리 캐시(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

