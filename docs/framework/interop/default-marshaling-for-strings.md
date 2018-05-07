---
title: 문자열에 대한 기본 마샬링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88604058bd460d80214be6051abef7dc561c7710
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="default-marshaling-for-strings"></a>문자열에 대한 기본 마샬링
<xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스는 마샬링 동작이 서로 유사합니다.  
  
 문자열은 COM 스타일 `BSTR` 형식 또는 null로 끝나는 문자열(null 문자로 끝나는 문자 배열)로 마샬링됩니다. 문자열 내의 문자는 유니코드(Windows 시스템에서 기본값) 또는 ANSI로 마샬링할 수 있습니다.  
  
 이 항목에서는 문자열 형식 마샬링에 대한 다음 정보를 제공합니다.  
  
-   [인터페이스에서 사용되는 문자열](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [플랫폼 호출에서 사용되는 문자열](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [구조체에서 사용되는 문자열](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [고정 길이 문자열 버퍼](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a>인터페이스에서 사용되는 문자열  
 다음 표에서는 비관리 코드에 대한 메서드 인수로 마샬링하는 경우 문자열 데이터 형식에 대한 마샬링 옵션을 보여 줍니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 COM 인터페이스로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.  
  
|열거형 형식|관리되지 않는 형식에 대한 설명|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`(기본값)|고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.|  
|`UnmanagedType.LPStr`|null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.LPWStr`|null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.|  
  
 이 표는 문자열에 적용됩니다. 그러나 <xref:System.Text.StringBuilder>에 사용할 수 있는 옵션은 `UnmanagedType.LPStr` 및 `UnmanagedType.LPWStr`뿐입니다.  
  
 다음 예제에서는 `IStringWorker` 인터페이스에서 선언된 문자열을 보여 줍니다.  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

다음 예제에서는 형식 라이브러리에서 설명된 해당 인터페이스를 보여 줍니다.

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a>플랫폼 호출에서 사용되는 문자열  
 플랫폼 호출은 문자열 인수를 복사하고 .NET Framework 형식(유니코드)을 플랫폼 관리되지 않는 형식으로 변환합니다. 문자열을 변경할 수 없으며, 호출이 반환될 때 관리되지 않는 메모리에서 관리되는 메모리로 다시 복사되지 않습니다.  
  
 다음 표에서는 플랫폼 호출의 메서드 인수로 마샬링하는 경우 문자열에 대한 마샬링 옵션을 보여 줍니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.  
  
|열거형 형식|관리되지 않는 형식에 대한 설명|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|고정 길이 및 ANSI 문자를 가진 COM 스타일 `BSTR`입니다.|  
|`UnmanagedType.BStr`|고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.|  
|`UnmanagedType.LPStr`|null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.LPTStr`|null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.LPWStr`|null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.TBStr`|고정 길이 및 플랫폼 종속 문자를 가진 COM 스타일 `BSTR`입니다.|  
|`VBByRefStr`|Visual Basic .NET에서 비관리 코드의 문자열을 변경하고 결과를 관리 코드에 반영되도록 하는 데 사용할 수 있는 값입니다. 이 값은 플랫폼 호출에만 지원됩니다. Visual Basic의 `ByVal` 문자열에 대한 기본값입니다.|  
  
 이 표는 문자열에 적용됩니다. 그러나 <xref:System.Text.StringBuilder>에 사용할 수 있는 옵션은 `LPStr`, `LPTStr` 및 `LPWStr`뿐입니다.  
  
 다음 형식 정의는 플랫폼 호출에 대한 `MarshalAsAttribute`의 올바른 사용을 보여 줍니다.  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a>구조체에서 사용되는 문자열  
 문자열은 구조체의 유효한 멤버지만 <xref:System.Text.StringBuilder> 버퍼는 구조체에서 유효하지 않습니다. 다음 표에서는 형식을 필드로 마샬링하는 경우 문자열 데이터 형식에 대한 마샬링 옵션을 보여 줍니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 필드로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.  
  
|열거형 형식|관리되지 않는 형식에 대한 설명|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.|  
|`UnmanagedType.LPStr`|null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.LPTStr`|null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.LPWStr`|null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.|  
|`UnmanagedType.ByValTStr`|고정 길이 문자 배열입니다. 배열 형식은 포함하는 구조체의 문자 집합에 의해 결정됩니다.|  
  
 `ByValTStr` 형식은 구조체 내에 나타나는 인라인 고정 길이 문자 배열에 사용됩니다. 다른 형식은 문자열에 대한 포인터를 포함하는 구조체 내에 포함된 문자열 참조에 적용됩니다.  
  
 포함하는 구조체에 적용된 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성의 `CharSet` 인수는 구조체에서 문자열의 문자 형식을 결정합니다. 다음 구조체 예에서는 문자열 참조 및 인라인 문자열뿐 아니라 ANSI, 유니코드 및 플랫폼 종속 문자를 포함합니다.  
  
### <a name="type-library-representation"></a>형식 라이브러리 표현  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 다음 코드 예제에서는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 동일한 구조체를 다양한 형식으로 정의하는 방법을 보여 줍니다.  
  
```vb  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _  
Structure StringInfoA  
<MarshalAs(UnmanagedType.LPStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _  
Structure StringInfoW  
<MarshalAs(UnmanagedType.LPWStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
<MarshalAs(UnmanagedType.BStr)> Public f3 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _  
Structure StringInfoT  
<MarshalAs(UnmanagedType.LPTStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a>고정 길이 문자열 버퍼  
 일부 환경에서는 고정 길이 문자 버퍼를 조작할 비관리 코드로 전달해야 합니다. 호출 수신자는 전달된 버퍼의 내용을 수정할 수 없기 때문에 이 경우 단순히 문자열을 전달하면 작동하지 않습니다. 문자열이 참조로 전달되는 경우 버퍼를 지정된 크기로 초기화할 수 있는 방법이 없습니다.  
  
 솔루션은 문자열 대신 <xref:System.Text.StringBuilder> 버퍼를 인수로 전달하는 것입니다. `StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다. 고정 길이로 초기화할 수도 있습니다. 예를 들어 `StringBuilder` 버퍼를 `N` 용량으로 초기화하는 경우 마샬러가 (`N`+1)자 크기의 버퍼를 제공합니다. +1은 `StringBuilder`에는 없는데 관리되지 않는 문자열에 null 종결자가 있다는 사실을 고려합니다.  
  
 예를 들어 Microsoft Win32 API `GetWindowText` 함수(Windows.h에서 정의됨)는 조작할 비관리 코드에 전달해야 하는 고정 길이 문자 버퍼입니다. `LpString`은 크기가 `nMaxCount`인 호출자 할당 버퍼를 가리킵니다. 호출자는 버퍼를 할당하고 `nMaxCount` 인수를 할당된 버퍼 크기로 설정해야 합니다. 다음 코드에서는 Windows.h에서 정의된 `GetWindowText` 함수 선언을 보여 줍니다.  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 `StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다. 다음 코드 예제에서는 `StringBuilder`를 고정 길이로 초기화할 수 있는 방법을 보여 줍니다.  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 마샬링 동작](default-marshaling-behavior.md)  
 [Blittable 형식 및 비 Blittable 형식](blittable-and-non-blittable-types.md)  
 [방향 특성](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))  
 [복사 및 고정](copying-and-pinning.md)
