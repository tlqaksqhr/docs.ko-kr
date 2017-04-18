---
title: "구조체 전달 | Microsoft Docs"
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
  - "플랫폼 호출, 관리되지 않는 함수 호출"
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 구조체 전달
대부분의 관리되지 않는 함수의 경우, 관리 코드에 정의된 구조체의 멤버\(Visual Basic의 사용자 정의 형식\) 또는 클래스의 멤버를 함수에 대한 매개 변수로 전달해야 합니다.  플랫폼 호출을 사용하여 구조체 또는 클래스를 비관리 코드에 전달하는 경우 원래 레이아웃 및 맞춤을 유지하면서 추가 정보를 제공해야 합니다.  이 단원에서는 서식이 지정된 형식을 정의하는 데 사용되는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성에 대해 설명합니다.  관리되는 구조체 및 클래스의 경우, **LayoutKind** 열거형에서 제공하는 몇 가지 예측 가능한 레이아웃 동작에서 선택할 수 있습니다.  
  
 이 항목에서 제시되는 개념의 핵심은 구조체와 클래스 형식 간의 중요한 차이입니다.  구조체는 값 형식이고 클래스는 참조 형식입니다. 클래스에서는 항상 메모리 간접 참조\(값에 대한 포인터\) 수준을 하나 이상 제공합니다.  다음 표의 첫째 열에 있는 시그니처에서 볼 수 있듯이 관리되지 않는 함수는 종종 간접 참조를 요청하기 때문에 이 차이는 중요합니다.  나머지 열에 있는 관리되는 구조체 및 클래스 선언은 선언에서 간접 참조 수준을 조정할 수 있는 정도를 보여 줍니다.  Visual Basic 및 Visual C\# 모두 선언을 지원합니다.  
  
|관리되지 않는 시그니처|관리되는 선언:                <br /> 간접 참조 없음               <br />  `Structure MyType`  <br />  `struct MyType;`|관리되는 선언:                <br /> 1 수준의 간접 참조               <br />  `Class MyType`  <br />  `class MyType;`|  
|------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> 0 수준의 간접 참조를 요청합니다.|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> 0 수준의 간접 참조를 추가합니다.|이미 1 수준의 간접 참조가 있기 때문에 불가능합니다.|  
|`DoWork(MyType* x);`<br /><br /> 1 수준의 간접 참조를 요청합니다.|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> 1 수준의 간접 참조를 추가합니다.|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> 0 수준의 간접 참조를 추가합니다.|  
|`DoWork(MyType** x);`<br /><br /> 2 수준의 간접 참조를 요청합니다.|**ByRef** **ByRef** 또는 `ref` `ref`는 사용할 수 없기 때문에 불가능합니다.|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> 1 수준의 간접 참조를 추가합니다.|  
  
 이 표에서는 플랫폼 호출 선언에 대한 다음과 같은 지침을 설명합니다.  
  
-   관리되지 않는 함수에 간접 참조를 요청하지 않으면 값으로 전달되는 구조체를 사용합니다.  
  
-   관리되지 않는 함수에 1 수준의 간접 참조를 요청하면 참조로 전달되는 구조체나 값으로 전달되는 클래스를 사용합니다.  
  
-   관리되지 않는 함수에 2 수준의 간접 참조를 요청하면 참조로 전달되는 클래스를 사용합니다.  
  
## 구조체 선언 및 전달  
 다음 예제에서는 관리 코드에서 `Point` 및 `Rect` 구조체를 정의하고 이들 형식을 User32.dll 파일의 **PtInRect** 함수에 대한 매개 변수로 전달하는 방법을 보여 줍니다.  **PtInRect**의 관리되지 않는 시그니처는 다음과 같습니다.  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 함수에는 RECT 형식에 대한 포인터가 필요하므로 Rect 구조체를 참조로 전달해야 합니다.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## 클래스 선언 및 전달  
 클래스에 고정 멤버 레이아웃이 있으면 클래스의 멤버를 관리되지 않는 DLL 함수에 전달할 수 있습니다.  다음 예제에서는 `MySystemTime` 클래스에 순차적으로 정의된 멤버를 User32.dll 파일의 **GetSystemTime**에 전달하는 방법을 보여 줍니다.  **GetSystemTime**의 관리되지 않는 시그니처는 다음과 같습니다.  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 값 형식과 달리 클래스에는 항상 1 수준 이상의 간접 참조가 있습니다.  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## 참고 항목  
 [DLL 함수 호출](../../../docs/framework/interop/calling-a-dll-function.md)   
 [StructLayoutAttribute 클래스](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [StructLayoutAttribute 클래스](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [FieldOffsetAttribute 클래스](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)