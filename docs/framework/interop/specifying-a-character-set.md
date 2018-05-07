---
title: 문자 집합 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1016a0c63a85919764271e01771ff8192341725c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-a-character-set"></a>문자 집합 지정
<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 문자열 마샬링을 제어하고 플랫폼 호출이 DLL에서 함수 이름을 찾는 방법을 결정합니다. 이 항목에서는 두 동작에 대해 모두 설명합니다.  
  
 일부 API는 문자열 인수를 사용하는 함수의 두 가지 버전인 narrow(ANSI) 및 wide(Unicode)를 내보냅니다. 예를 들어 Win32 API에는 **MessageBox** 함수에 대한 다음 진입점 이름이 포함됩니다.  
  
-   **MessageBoxA**  
  
     진입점 이름에 “A”를 추가하여 구분되는 1바이트 문자 ANSI 형식을 제공합니다. **MessageBoxA** 호출은 Windows 95 및 Windows 98 플랫폼에서 일반적인 경우와 마찬가지로 항상 문자열을 ANSI 형식으로 마샬링합니다.  
  
-   **MessageBoxW**  
  
     진입점 이름에 “W”를 추가하여 구분되는 2바이트 문자 유니코드 형식을 제공합니다. **MessageBoxW** 호출은 Windows NT, Windows 2000 및 Windows XP 플랫폼에서 일반적인 경우와 마찬가지로 항상 문자열을 유니코드 형식으로 마샬링합니다.  
  
## <a name="string-marshaling-and-name-matching"></a>문자열 마샬링 및 이름 일치  
 **CharSet** 필드는 다음 값을 허용합니다.  
  
 **CharSet.Ansi**(기본값)  
  
-   문자열 마샬링  
  
     플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 ANSI 형식으로 마샬링합니다.  
  
-   이름 일치  
  
     <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 필드가 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 기본값인 **true**이면 플랫폼 호출이 지정한 이름만 검색합니다. 예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.  
  
     **ExactSpelling** 필드가 C++ 및 C#의 기본값인 **false**이면 플랫폼 호출은 올바른 별칭(**MessageBox**)을 먼저 검색한 다음, 올바른 별칭을 찾을 수 없는 경우 잘못된 이름(**MessageBoxA**)을 검색합니다. ANSI 이름 일치 동작은 유니코드 이름 일치 동작과 다릅니다.  
  
 **CharSet.Unicode**  
  
-   문자열 마샬링  
  
     플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 유니코드 형식으로 복사합니다.  
  
-   이름 일치  
  
     **ExactSpelling** 필드가 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 기본값인 **true**이면 플랫폼 호출이 지정한 이름만 검색합니다. 예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.  
  
     **ExactSpelling** 필드가 C++ 및 C#의 기본값인 **false**이면 플랫폼 호출은 잘못된 이름(**MessageBoxW**)을 먼저 검색한 다음, 잘못된 이름을 찾을 수 없는 경우 올바른 별칭(**MessageBox**)을 검색합니다. 유니코드 이름 일치 동작은 ANSI 이름 일치 동작과 다릅니다.  
  
 **CharSet.Auto**  
  
-   플랫폼 호출이 대상 플랫폼에 따라 런타임에 ANSI와 유니코드 중에서 선택합니다.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Visual Basic에서 문자 집합 지정  
 다음 예제에서는 매번 서로 다른 문자 집합 동작을 사용하여 **MessageBox** 함수를 세 번 선언합니다. **Ansi**, **유니코드** 또는 **자동** 키워드를 선언문에 추가하여 Visual Basic에서 문자 집합 동작을 지정할 수 있습니다.  
  
 첫 번째 선언문과 같이 문자 집합 키워드를 생략하면 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본적으로 ANSI 문자 집합으로 설정됩니다. 예제에서 두 번째 문과 세 번째 문은 키워드를 사용해서 명시적으로 문자 집합을 지정합니다.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a>C# 및 C++에서 문자 집합 지정  
 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본 문자 집합을 ANSI 또는 유니코드로 식별합니다. 문자 집합은 메서드에 대한 문자열 인수를 마샬링하는 방법을 제어합니다. 다음 형식 중 하나를 사용하여 문자 집합을 나타냅니다.  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 다음 예제에서는 문자 집합을 지정하는 **MessageBox** 함수의 세 가지 관리되는 정의를 보여 줍니다. 첫 번째 정의에서는 생략에 의해 **CharSet** 필드가 기본값인 ANSI 문자 집합으로 설정됩니다.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [플랫폼 호출 예제](../../../docs/framework/interop/platform-invoke-examples.md)  
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
