---
title: "Interop 특성 적용 | Microsoft Docs"
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
  - ".NET Framework, COM에 구성 요소 노출"
  - "특성[.NET Framework], 변환 도구"
  - "특성[.NET Framework], 디자인 타임 기능"
  - "특성[.NET Framework], interop 관련"
  - "COM interop, 특성 적용"
  - "COM interop, COM 구성 요소 게시"
  - "변환 도구 특성"
  - "디자인 타임 특성"
  - "비관리 코드와의 상호 운용, 특성 적용"
  - "비관리 코드와의 상호 운용, .NET Framework 구성 요소 게시"
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Interop 특성 적용
<xref:System.Runtime.InteropServices> 네임스페이스에서는 세 개의 interop 관련 특성인 사용자가 디자인 타임에 적용하는 특성, 변환 프로세스 동안 COM interop 도구 및 API에서 적용하는 특성, 사용자 또는 COM interop에서 적용하는 특성을 제공합니다.  
  
 관리 코드에 특성을 적용하는 작업에 익숙하지 않은 경우에는 먼저 [특성을 사용하여 메타데이터 확장](../../../docs/standard/attributes/index.md)을 참조하십시오.  다른 모든 사용자 지정 특성과 마찬가지로 interop 관련 특성도 형식, 메서드, 속성, 매개 변수, 필드 및 기타 멤버에 적용할 수 있습니다.  
  
## 디자인 타임 특성  
 디자인 타임 특성을 사용하면 COM interop 도구 및 API에서 수행하는 변환 프로세스의 결과를 조정할 수 있습니다.  다음 표에서는 관리 소스 코드에 적용할 수 있는 특성에 대해 설명합니다.  경우에 따라서는 이 표에 설명된 특성을 COM interop 도구에서도 적용할 수도 있습니다.  
  
|특성|설명|  
|--------|--------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|자동화 마샬러 또는 사용자 지정 프록시 및 스텁을 사용하여 형식을 마샬링할지 여부를 지정합니다.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|클래스에 대해 생성되는 인터페이스의 형식을 제어합니다.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|형식 라이브러리에서 가져온 원래 coclass의 CLSID를 식별합니다.<br /><br /> 일반적으로 COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|COM 형식 라이브러리에서 coclass 또는 인터페이스 정의를 가져왔음을 나타냅니다.  런타임에서는 형식을 활성화하고 마샬링하는 방법을 이 특성을 통해 확인합니다.  이 특성을 사용하면 형식을 형식 라이브러리로 다시 내보낼 수 없습니다.<br /><br /> 일반적으로 COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|사용자가 작성한 코드가 등록 프로세스 동안 실행될 수 있도록, COM에서 사용할 어셈블리를 등록할 때 메서드를 호출해야 함을 나타냅니다.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|클래스에 대한 이벤트의 소스인 인터페이스를 나타냅니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|사용자가 작성한 코드가 등록 취소 프로세스 동안 실행될 수 있도록, COM에서 사용할 어셈블리의 등록을 취소할 때 메서드를 호출해야 함을 나타냅니다.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|특성 값이 **false**인 경우 형식이 COM에 표시되지 않도록 형식을 렌더링합니다.  이 특성을 개별 형식 또는 어셈블리 전체에 적용하여 COM에서의 표시 여부를 제어할 수 있습니다.  기본적으로 모든 관리되는 공용 형식은 표시되기 때문에 이들 형식을 표시하기 위해 이 특성을 사용할 필요는 없습니다.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|메서드 또는 필드의 COM DISPID\(디스패치 식별자\)를 지정합니다.  이 특성에는 메서드, 필드 또는 속성에 대한 DISPID가 들어 있습니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|**StructLayoutAttribute**와 함께 사용되고 **LayoutKind**가 Explicit로 설정된 경우, 클래스 내에 있는 필드의 실제 위치를 나타냅니다.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|클래스, 인터페이스 또는 형식 라이브러리 전체의 GUID\(Globally Unique Identifier\)를 지정합니다.  특성에 전달되는 문자열은 **System.Guid** 형식의 생성자 인수 형식이어야 합니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|[IDispatchImpAttribute](frlrfsystemruntimeinteropservicesidispatchimplattributeclasstopic)|이중 인터페이스 및 dispinterface를 COM에 노출시키기 위해 공용 언어 런타임에서 사용하는 **IDispatch** 인터페이스 구현을 나타냅니다.|  
|<xref:System.Runtime.InteropServices.InAttribute>|데이터가 호출자로 마샬링되어야 함을 나타냅니다.  특성 매개 변수에 사용될 수 있습니다.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|관리되는 인터페이스가 COM 클라이언트에 노출될 때 해당 인터페이스가 이중 인터페이스, IDispatch, 또는 IUnknown에서 파생되었는지 제어합니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|관리되지 않는 메서드 시그니처에 LCID 매개 변수가 필요함을 나타냅니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|관리 코드와 비관리 코드 간에 필드 또는 매개 변수의 데이터가 마샬링되는 방법을 나타냅니다.  각 데이터 형식에는 기본 마샬링 동작이 있기 때문에 이 특성은 항상 선택적입니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|매개 변수가 선택적임을 나타냅니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|필드 또는 매개 변수의 데이터가, 호출되는 개체로부터 호출자에게 다시 마샬링되어야 함을 나타냅니다.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|HRESULT 또는 상호 운용 호출 시 일반적으로 발생하는 retval 시그니처 변환을 표시하지 않습니다.  이 특성은 형식 라이브러리 내보내기 및 마샬링에 영향을 줍니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|.NET Framework 클래스의 ProgID를 지정하며,  특성 클래스에 사용될 수 있습니다.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|클래스에 있는 필드의 실제 레이아웃을 제어합니다.<br /><br /> COM interop 도구에서도 이 특성을 적용할 수 있습니다.|  
  
## 변환 도구 특성  
 다음 표에서는 COM interop 도구에서 변환 프로세스 동안 적용하는 특성에 대해 설명합니다.  사용자는 다음 특성을 디자인 타임에 적용할 수 없습니다.  
  
|특성|설명|  
|--------|--------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|매개 변수 또는 필드 형식에 대한 COM 별칭을 나타냅니다.  특성 매개 변수, 필드 또는 반환 값에 사용될 수 있습니다.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|클래스 또는 인터페이스에 대한 정보를 형식 라이브러리에서 어셈블리로 가져오는 동안 해당 정보가 손실되었음을 나타냅니다.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|이벤트 인터페이스의 메서드를 구현하는 소스 인터페이스 및 클래스를 식별합니다.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|COM 형식 라이브러리에서 어셈블리를 가져왔음을 나타냅니다.  이 특성은 원래 형식 라이브러리의 형식 라이브러리 정의를 포함합니다.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|이 함수를 위해 COM 형식 라이브러리에서 가져온 **FUNCFLAGS**를 포함합니다.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|이 형식을 위해 COM 형식 라이브러리에서 가져온 **TYPEFLAGS**를 포함합니다.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|이 변수를 위해 COM 형식 라이브러리에서 가져온 **VARFLAGS**를 포함합니다.|  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices>   
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [특성](../../../docs/standard/attributes/index.md)   
 [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [COM에서 사용할 어셈블리의 패키징](../../../docs/framework/interop/packaging-an-assembly-for-com.md)