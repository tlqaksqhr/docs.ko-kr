---
title: "플랫폼 호출 예제 | Microsoft Docs"
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
  - "COM interop, 플랫폼 호출"
  - "DLL 함수"
  - "예제[.NET Framework], 플랫폼 호출"
  - "비관리 코드와의 상호 운용, 플랫폼 호출"
  - "플랫폼 호출, 예제"
  - "관리되지 않는 함수"
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 플랫폼 호출 예제
다음 예제에서는 간단한 문자열을 인수로 전달하여 User32.dll에서 **MessageBox** 함수를 정의하고 호출하는 방법을 보여 줍니다.  아래 예제에서는 대상 플랫폼에 따라 문자 너비 및 문자열 마샬링이 결정되도록 [DllImportAttribute.CharSet Field](frlrfSystemRuntimeInteropServicesDllImportAttributeClassCharSetTopic) 필드가 **Auto**로 설정되어 있습니다.  
  
 이 예제는 Visual Basic, C\# 및 C\+\+에서도 동일합니다.  페이지의 왼쪽 위 모퉁이에 있는 언어 필터 단추![](../../../docs/framework/interop/media/filter2.gif "Filter2")를 클릭하면 모든 예제를 표시할 수 있습니다.  추가 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)을 참조하십시오.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
       ByVal caption As String, ByVal Typ As Integer) As IntPtr  
End Class  
  
Public Class HelloWorld      
    Public Shared Sub Main()  
        Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0)  
    End Sub  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
     [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern IntPtr MessageBox(int hWnd, String text,   
                     String caption, uint type);  
}  
  
public class HelloWorld {  
    public static void Main() {  
       Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0);  
    }  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" IntPtr MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
void main(void) {  
     String* pText = L"Hello World!";  
     String* pCaption = L"Platform Invoke Sample";  
     MessageBox(0, pText, pCaption, 0);  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [문자 집합 지정](../../../docs/framework/interop/specifying-a-character-set.md)