---
title: "진입점 지정 | Microsoft Docs"
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
  - "플랫폼 호출의 특성 필드, EntryPoint"
  - "EntryPoint 필드"
  - "플랫폼 호출, 특성 필드"
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 진입점 지정
진입점은 DLL에서의 함수 위치를 식별합니다.  관리되는 프로젝트에서, 대상 함수의 원래 이름 또는 서수 진입점은 상호 운용 경계 내에서 해당 함수를 식별하는 데 사용됩니다.  진입점을 다른 이름에 매핑하면 함수의 이름을 바꿀 수도 있습니다.  
  
 다음 경우에는 함수 이름을 바꿀 수 있습니다.  
  
-   대\/소문자를 구분하는 API 함수 이름을 사용하지 않으려는 경우  
  
-   기존 명명 규칙을 따라야 하는 경우  
  
-   동일한 DLL 함수의 여러 버전을 선언하여 다른 데이터 형식을 사용하는 함수를 적용하려는 경우  
  
-   ANSI 및 유니코드 버전이 들어 있는 API를 간단하게 사용하려는 경우  
  
 이 단원에서는 관리 코드에서 DLL 함수의 이름을 바꾸는 방법을 보여 줍니다.  
  
## Visual Basic에서 함수 이름 바꾸기  
 Visual Basic에서는 **Declare** 문에 **Function** 키워드를 사용하여 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> 필드를 설정합니다.  다음 예제에서는 기본 선언을 보여 줍니다.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 다음 예제처럼 정의에 **Alias** 키워드를 넣어 **MessageBox** 진입점을 **MsgBox**로 바꿀 수 있습니다.  두 예제 모두에 **Auto** 키워드를 넣었기 때문에 진입점의 문자 집합 버전을 지정할 필요가 없습니다.  문자 집합의 선택에 대한 자세한 내용은 [문자 집합 지정](../../../docs/framework/interop/specifying-a-character-set.md)을 참조하십시오.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## C\# 및 C\+\+에서 함수 이름 바꾸기  
 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> 필드를 사용하여 DLL 함수를 이름이나 서수로 지정할 수 있습니다.  메서드 정의의 함수 이름이 DLL의 진입점과 동일한 경우에는 **EntryPoint** 필드를 사용하여 함수를 명시적으로 식별하지 않아도 되지만,  함수 이름과 DLL 진입점이 다른 경우에는 다음 특성 폼 중 하나를 사용하여 함수의 이름 또는 서수를 지정해야 합니다.  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 서수에 파운드 기호\(\#\)를 접두사로 붙여야 합니다.  
  
 다음 예제에서는 **EntryPoint** 필드를 사용하여 코드에서 **MessageBoxA**를 **MsgBox**로 바꾸는 방법을 보여 줍니다.  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [플랫폼 호출 예제](../../../docs/framework/interop/platform-invoke-examples.md)   
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)