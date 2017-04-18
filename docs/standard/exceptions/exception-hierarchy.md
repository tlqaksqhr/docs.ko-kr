---
title: "예외 계층 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "예외 형식"
  - "런타임 예외"
  - "기본 예외"
  - "ApplicationException 클래스"
  - "공용 언어 런타임 예외"
  - "COM interop, 예외"
  - "예외 계층"
ms.assetid: f7d68675-be06-40fb-a555-05f0c5a6f66b
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# 예외 계층
실행 중인 프로그램에 의해 생성된 예외와 공용 언어 런타임에 의해 생성되는 예외 두 가지 예외가 있습니다. 또한 응용 프로그램이나 런타임에 의해 발생될 수 있는 예외 계층이 있습니다.  
  
 <xref:System.Exception?displayProperty=fullName> 클래스는 예외에 대 한 기본 클래스입니다. 몇 가지 예외 클래스에서 직접 상속 <xref:System.Exception>을 포함 하 여 <xref:System.ApplicationException> 및 <xref:System.SystemException>합니다. 이 두 클래스는 거의 모든 런타임 예외에 대한 기초를 형성합니다.  
  
 직접 파생 되는 대부분의 예외 <xref:System.Exception> 기능 및 새 구성원을 추가 합니다. 예를 들어는 <xref:System.InvalidCastException> 클래스 계층 구조는 다음과 같습니다.  
  
 <xref:System.Object> <xref:System.Exception> <xref:System.SystemException> <xref:System.InvalidCastException>  
  
 런타임에서 throw의 적절 한 파생된 클래스로 <xref:System.SystemException> 오류가 발생 한 경우. 이러한 오류는 실패한 런타임 검사로 인해 발생하며(예: 배열 범위를 벗어나는 오류) 메서드 실행 중에 발생할 수 있습니다. 이러한 예외를 파생 해야 새 예외를 만드는 응용 프로그램을 디자인 하는 경우는 <xref:System.Exception> 클래스입니다. Catch 하는 권장 되지 않습니다는 <xref:System.SystemException>, 바람직한 프로그래밍 관행 throw 하는 한 <xref:System.SystemException> 응용 프로그램에 있습니다.  
  
 가장 심각한 예외-런타임에서 또는 복구할 수 없는 상황에서 throw 된 — 포함 <xref:System.ExecutionEngineException>, <xref:System.StackOverflowException>, 및 <xref:System.OutOfMemoryException>합니다.  
  
 파생 되는 상호 운용 예외 <xref:System.SystemException> 를 통해 더욱 확장 하 고 <xref:System.Runtime.InteropServices.ExternalException>합니다. 예를 들어 <xref:System.Runtime.InteropServices.COMException> COM interop 작업 하는 동안 throw 된 예외에서 파생 되 고 <xref:System.Runtime.InteropServices.ExternalException>합니다. <xref:System.ComponentModel.Win32Exception> 및 <xref:System.Runtime.InteropServices.SEHException> 에서 파생 되는 경우도 <xref:System.Runtime.InteropServices.ExternalException>합니다.  
  
## <a name="hierarchy-of-runtime-exceptions"></a>런타임 예외의 계층 구조  
 런타임 예외에서 파생의 기본 집합이 <xref:System.SystemException> 개별 명령을 실행 하는 경우 throw 됩니다. 다음 표에서는 런타임에서 제공하는 표준 예외와 파생된 클래스를 만들어야 하는 조건을 계층적으로 나열하여 보여줍니다.  
  
|예외 형식|기본 형식|설명|예제|  
|--------------------|---------------|-----------------|-------------|  
|[예외](../../../docs/standard/exceptions/exception-class-and-properties.md)|<xref:System.Object>|모든 예외의 기본 클래스.|없음(이 예외의 파생된 클래스 사용).|  
|<xref:System.SystemException>|<xref:System.Exception>|모든 런타임 생성 오류에 대한 기본 클래스.|없음(이 예외의 파생된 클래스 사용).|  
|<xref:System.IndexOutOfRangeException>|<xref:System.SystemException>|배열이 올바르지 않게 인덱싱된 경우에만 런타임에서 발생됩니다.|유효 범위를 벗어난 배열 인덱싱:<br /><br /> `var i = arr[arr.Length + 1];`<br /><br /> `Dim i = arr(arr.Length + 1)`|  
|<xref:System.NullReferenceException>|<xref:System.SystemException>|null 개체가 참조되는 경우에만 런타임에서 발생됩니다.|`object o = null; string s = o.ToString();`<br /><br /> `Dim o As Object = Nothing Dim s As String = o.ToString()`|  
|<xref:System.AccessViolationException>|<xref:System.SystemException>|잘못된 메모리에 액세스하는 경우에만 런타임에서 발생됩니다.|비관리 코드 또는 안전하지 않은 관리 코드를 상호 운용하고 잘못된 포인터가 사용되는 경우에 발생합니다.|  
|<xref:System.InvalidOperationException>|<xref:System.SystemException>|잘못된 상태에 있는 경우에 메서드에서 발생됩니다.|열거자의 호출 `GetNext` 메서드 후 기본 컬렉션에서 항목을 제거 합니다.|  
|<xref:System.ArgumentException>|<xref:System.SystemException>|모든 인수 예외에 대한 기본 클래스.|없음(이 예외의 파생된 클래스 사용).|  
|<xref:System.ArgumentNullException>|<xref:System.ArgumentException>|인수에 Null을 허용하지 않는 메서드에서 발생됩니다.|`String s = null; int i = "Calculate".IndexOf(s);`<br /><br /> `Dim s As String = Nothing Dim i As Integer = "Calculate".IndexOf(s)`|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.ArgumentException>|인수가 지정된 범위에 있는지 확인하는 메서드에서 발생됩니다.|`String s = "string"; s = s.Substring(s.Length + 1);`<br /><br /> `Dim s As String = "string" s = s.Substring(s.Length + 1)`|  
|<xref:System.Runtime.InteropServices.ExternalException>|<xref:System.SystemException>|런타임 외부의 환경에서 발생하거나 대상이 되는 예외에 대한 기본 클래스.|없음(이 예외의 파생된 클래스 사용).|  
|<xref:System.Runtime.InteropServices.COMException>|<xref:System.Runtime.InteropServices.ExternalException>|COM HRESULT 정보를 캡슐화하는 예외.|COM interop에 사용됩니다.|  
|<xref:System.Runtime.InteropServices.SEHException>|<xref:System.Runtime.InteropServices.ExternalException>|Win32 구조의 예외 처리 정보를 캡슐화하는 예외.|비관리 코드 interop에 사용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Exception 클래스 및 속성](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [예외에 대 한 모범 사례](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [예외](../../../docs/standard/exceptions/index.md)