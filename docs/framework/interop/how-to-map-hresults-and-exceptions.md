---
title: "방법: HRESULT 및 예외 매핑 | Microsoft Docs"
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
  - "COM interop, 예외"
  - "COM interop, HRESULT"
  - "예외, HRESULT"
  - "HRESULT"
  - "비관리 코드와의 상호 운용, 예외"
  - "비관리 코드와의 상호 운용, HRESULT"
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: HRESULT 및 예외 매핑
COM 메서드는 HRESULT를 반환하여 오류를 보고하고 .NET 메서드는 예외를 throw하여 보고합니다.  런타임은 이 둘 사이의 전환을 처리합니다.  .NET Framework의 각 예외 클래스는 HRESULT에 매핑됩니다.  
  
 사용자 정의 예외 클래스는 적절한 HRESULT를 지정할 수 있습니다.  이 예외 클래스는 예외 개체에 **HResult** 필드를 설정하여 예외를 생성할 때 반환되는 HRESULT를 동적으로 변경할 수 있습니다.  예외에 대한 추가 정보는 관리되지 않는 프로세스에서 .NET 개체에 구현되는 **IErrorInfo** 인터페이스를 통해 클라이언트에 제공됩니다.  
  
 **System.Exception**을 확장하는 클래스를 만드는 경우 생성하는 동안 HRESULT 필드를 설정해야 합니다.  그렇지 않으면 기본 클래스에서 HRESULT 값을 할당합니다.  예외 생성자에서 값을 제공하여 새 예외 클래스를 기존의 HRESULT에 매핑할 수 있습니다.  
  
 런타임은 스레드에 `IErrorInfo`가 있는 경우 `HRESULT`를 무시하기도 합니다.  이러한 동작은 `HRESULT`와 `IErrorInfo`가 동일한 오류를 나타내지 않는 경우에 발생할 수 있습니다.   ``  
  
### 새 예외 클래스를 만들어 HRESULT에 매핑하려면  
  
1.  다음 코드를 사용하여 `NoAccessException`이라는 새 예외 클래스를 만든 다음 HRESULT `E_ACCESSDENIED`에 매핑합니다.  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;   
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 관리 코드와 비관리 코드를 동시에 사용하는 프로그램\(모든 프로그래밍 언어 사용 가능\)을 발견할 수 있습니다.  예를 들어 다음 코드 예제에서 사용자 지정 마샬러는 **Marshal.ThrowExceptionForHR\(int HResult\)** 메서드를 사용하여 특정 HRESULT 값으로 예외를 throw합니다.  이 메서드는 HRESULT를 찾아서 적절한 예외 형식을 생성합니다.  예를 들어 다음 코드의 HRESULT는 **ArgumentException**을 생성합니다.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 다음 표에서는 각 HRESULT에서 .NET Framework의 해당 예외 클래스로의 전체 매핑을 제공합니다.  
  
|HRESULT|.NET 예외|  
|-------------|-------------|  
|**MSEE\_E\_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR\_E\_APPLICATION**|**ApplicationException**|  
|**COR\_E\_ARGUMENT 또는 E\_INVALIDARG**|**ArgumentException**|  
|**COR\_E\_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR\_E\_ARITHMETIC 또는 ERROR\_ARITHMETIC\_OVERFLOW**|**ArithmeticException**|  
|**COR\_E\_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR\_E\_BADIMAGEFORMAT 또는 ERROR\_BAD\_FORMAT**|**BadImageFormatException**|  
|**COR\_E\_COMEMULATE\_ERROR**|**COMEmulateException**|  
|**COR\_E\_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR\_E\_CORE**|**CoreException**|  
|**NTE\_FAIL**|**CryptographicException**|  
|**COR\_E\_DIRECTORYNOTFOUND 또는 ERROR\_PATH\_NOT\_FOUND**|**DirectoryNotFoundException**|  
|**COR\_E\_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR\_E\_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR\_E\_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR\_E\_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR\_E\_EXCEPTION**|**Exception**|  
|**COR\_E\_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR\_E\_FIELDACCESS**|**FieldAccessException**|  
|**COR\_E\_FILENOTFOUND 또는 ERROR\_FILE\_NOT\_FOUND**|**FileNotFoundException**|  
|**COR\_E\_FORMAT**|**FormatException**|  
|**COR\_E\_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR\_E\_INVALIDCAST 또는 E\_NOINTERFACE**|**InvalidCastException**|  
|**COR\_E\_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR\_E\_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR\_E\_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR\_E\_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR\_E\_IO**|**IOException**|  
|**COR\_E\_MEMBERACCESS**|**AccessException**|  
|**COR\_E\_METHODACCESS**|**MethodAccessException**|  
|**COR\_E\_MISSINGFIELD**|**MissingFieldException**|  
|**COR\_E\_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR\_E\_MISSINGMEMBER**|**MissingMemberException**|  
|**COR\_E\_MISSINGMETHOD**|**MissingMethodException**|  
|**COR\_E\_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR\_E\_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E\_NOTIMPL**|**NotImplementedException**|  
|**COR\_E\_NOTSUPPORTED**|**NotSupportedException**|  
|**COR\_E\_NULLREFERENCE 또는 E\_POINTER**|**NullReferenceException**|  
|**COR\_E\_OUTOFMEMORY 또는**<br /><br /> **E\_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR\_E\_OVERFLOW**|**OverflowException**|  
|**COR\_E\_PATHTOOLONG 또는 ERROR\_FILENAME\_EXCED\_RANGE**|**PathTooLongException**|  
|**COR\_E\_RANK**|**RankException**|  
|**COR\_E\_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR\_E\_REMOTING**|**RemotingException**|  
|**COR\_E\_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR\_E\_SECURITY**|**SecurityException**|  
|**COR\_E\_SERIALIZATION**|**SerializationException**|  
|**COR\_E\_STACKOVERFLOW 또는 ERROR\_STACK\_OVERFLOW**|**StackOverflowException**|  
|**COR\_E\_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR\_E\_SYSTEM**|**SystemException**|  
|**COR\_E\_TARGET**|**TargetException**|  
|**COR\_E\_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR\_E\_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR\_E\_THREADABORTED**|**ThreadAbortException**|  
|**COR\_E\_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR\_E\_THREADSTATE**|**ThreadStateException**|  
|**COR\_E\_THREADSTOP**|**ThreadStopException**|  
|**COR\_E\_TYPELOAD**|**TypeLoadException**|  
|**COR\_E\_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR\_E\_VERIFICATION**|**VerificationException**|  
|**COR\_E\_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR\_E\_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**다른 모든 HRESULT**|**COMException**|  
  
 확장된 오류 정보를 검색하려면 관리되는 클라이언트가 생성된 예외 개체의 필드를 검토해야 합니다.  예외 개체에서 오류에 관한 유용한 정보를 제공하기 위해 COM 개체는 **IErrorInfo** 인터페이스를 구현해야 합니다.  런타임은 **IErrorInfo**에서 제공하는 정보를 사용하여 예외 개체를 초기화합니다.  
  
 COM 개체에서 **IErrorInfo**를 지원하지 않는 경우 런타임은 기본값을 사용하여 예외 개체를 초기화합니다.  다음 표에서는 예외 개체와 관련된 각 필드를 나열하고 COM 개체가 **IErrorInfo**를 지원하는 경우 기본 정보의 소스를 식별합니다.  
  
 런타임은 스레드에 `IErrorInfo`가 있는 경우 `HRESULT`를 무시하기도 합니다.  이러한 동작은 `HRESULT`와 `IErrorInfo`가 동일한 오류를 나타내지 않는 경우에 발생할 수 있습니다.   ``  
  
|예외 필드|COM의 정보 소스|  
|-----------|----------------|  
|**ErrorCode**|호출에서 반환된 HRESULT|  
|**HelpLink**|**IErrorInfo\-\>HelpContext**가 0이 아닌 경우 **IErrorInfo\-\>GetHelpFile**, "\#", **IErrorInfo\-\>GetHelpContext**를 연결하여 문자열을 구성합니다.  그렇지 않은 경우에는 **IErrorInfo\-\>GetHelpFile**에서 문자열이 반환됩니다.|  
|**InnerException**|항상 null 참조\(Visual Basic에서는 **Nothing**\)|  
|**메시지**|**IErrorInfo\-\>GetDescription**에서 반환된 문자열|  
|**소스**|**IErrorInfo\-\>GetSource**에서 반환된 문자열|  
|**StackTrace**|스택 추적|  
|**TargetSite**|실패한 HRESULT를 반환한 메서드의 이름|  
  
 **Message**, **Source** 및 **StackTrace**와 같은 예외 필드는 **StackOverflowException**에 사용할 수 없습니다.  
  
## 참고 항목  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ko-kr/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [예외](../../../docs/standard/exceptions/index.md)