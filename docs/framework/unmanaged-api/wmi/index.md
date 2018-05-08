---
title: WMI 및 성능 카운터 (관리 되지 않는 API 참조)
description: .NET Framework 요약 API 관리 되지 않는 WMI 및 성능 카운터 정보에 대 한 합니다.
author: rpetrusha
ms.author: ronpet
ms.date: 11/06/2017
ms.openlocfilehash: 2007c8aa74e1ccf3c4753343ac633b67a36daeb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Windows Management Instrumentation (WMI) 및 성능 카운터 (관리 되지 않는 API 참조)

성능 카운터 및.NET Framework WMI 관리 되지 않는 API에 대 한 호출을 래핑하는 함수의 집합으로 구성 된 [네이티브 Windows Management Instrumentation API](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx)합니다. 도구 및 관리 하 고 원격 컴퓨터 시스템을 모니터링 하는 라이브러리를 개발할 수 있습니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
API에는 다음과 같은 기능에 포함 됩니다.

| 함수 | 설명 |
|---------|---------|
| [BeginEnumeration 함수](beginenumeration.md) | WMI 개체 속성의 열거형의 시작 부분에 열거자를 다시 설정합니다. |
| [BeginMethodEnumeration 함수](beginmethodenumeration.md) |  개체에 대해 사용할 수 있는 방법의 열거형을 시작합니다. |
| [BlessIWbemServices 함수](blessiwbemservices.md) | 사용자 자격 증명이 지정된 IWbemServices 클래스에 대 한 액세스를 허용 하는지 여부를 나타냅니다. |
| [BlessIWbemServicesObject 함수](blessiwbemservicesobject.md) | 사용자 자격 증명 지정된 IWbem 서비스 개체에 대 한 액세스를 허용 하는지 여부를 나타냅니다. |
| [복제 함수](clone.md) | 새 개체는 현재 개체의 전체 복제를 반환 합니다. |
| [CloneEnumWbemClassObject 함수](cloneenumwbemclassobject.md) | 열거형의 현재 위치를 유지 하는 열거자의 논리적 복사본을 만듭니다. |
| [CompareTo 함수](compareto.md) | 다른 Windows 관리 개체에 개체를 비교합니다. |
| [ConnectServerWmi 함수](connectserverwmi.md) | 지정된 된 컴퓨터에서 DCOM 통해 WMI 네임 스페이스에 연결을 만듭니다. |
| [CreateClassEnumWmi 함수](createclassenumwmi.md) | 지정 된 선택 조건과 일치 하는 모든 클래스에 대 한 열거자를 반환 합니다. |
| [CreateInstanceEnumWmi 함수](createinstanceenumwmi.md) | 인스턴스로만 구성 되어 지정된 된 클래스의 지정 된 선택 기준에 맞는 반환 하는 열거자를 반환 합니다. |
| [Delete 함수](delete.md) | 클래스 정의 및 모든 해당 한정자 중에서 지정된 된 속성을 삭제합니다. |
| [DeleteMethod 함수](deletemethod.md) | CIM 클래스 정의에서 지정된 된 메서드를 삭제합니다. |
| [EndEnumeration 함수](endenumeration.md) | 열거형 시퀀스를 종료합니다. | 
| [EndMethodEnumeration 함수](endmethodenumeration.md) | 호출 하 여 시작 하는 열거형 시퀀스를 마칩니다.는 [BeginMethodEnumeration 함수](beginmethodenumeration.md)합니다. |
| [ExecNotificationQueryWmi 함수](execnotificationquerywmi.md) | 이벤트를 수신 하는 쿼리를 실행 합니다. |
| [ExecQueryWmi 함수](execquerywmi.md) | 개체를 검색 하는 쿼리를 실행 합니다. |
| [FormatFromRawValue 함수](formatfromrawvalue.md) | 시간 기반 형식 변환 되 면 지정된 된 형식으로 원시 성능 데이터 값을 하나 또는 두 개의 원시 성능 데이터 값으로 변환 합니다. | 
| [Get 함수](get.md) | 있는 경우 지정 된 속성 값을 검색 합니다. |
| [GetCurrentApartmentType 함수](getcurrentapartmenttype.md) | 아파트 호출자에 게 실행 되는 형식을 검색 합니다. |
| [GetDemultiplexedStub 함수](getdemultiplexedstub.md) | Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다. |
| [GetErrorInfo 함수](geterrorinfo.md) | 이전 함수 호출에서 오류 정보를 검색합니다. | 
| [GetMethod 함수](getmethod.md) | 지정 된 메서드에 대 한 정보를 검색합니다. | 
| [GetMethodOrigin 함수](getmethodorigin.md) | 메서드 선언 되는 클래스를 결정 합니다. |
| [GetMethodQualifierSet 함수](getmethodqualifierset.md) | 특정 방법에 대해 설정할 한정자를 검색 합니다. |
| [GetNames 함수](getnames.md) | 하위 집합 또는 모든 개체의 속성 이름을 검색합니다. |
| [GetObjectText 함수](getobjecttext.md) | MOF 구문으로 개체의 텍스트 렌더링을 반환 합니다. | 
| [GetPropertyHandle 함수](getpropertyhandle.md) | 속성을 식별 하는 고유한 핸들을 반환 합니다. |
| [GetPropertyOrigin 함수](getpropertyorigin.md) | 속성 선언 되는 클래스를 결정 합니다. |
| [GetPropertyQualifierSet 함수](getpropertyqualifierset.md) | 특정 속성에 대해 설정할 한정자를 검색 합니다.  |
| [GetQualifierSet 함수](getqualifierset.md) | 클래스 인스턴스 또는 클래스 정의 대 한 한정자를 검색 합니다. |
| [InheritsFrom 함수](inheritsfrom.md) | 현재 클래스 또는 인스턴스를 지정 된 부모 클래스에서 파생 있는지 여부를 결정 합니다. |
| [Initialize 함수](initialize.md) | WMI 초기화를 수행 합니다. |
| [Next 함수](next.md) | 열거형에서 다음 속성을 검색합니다. | 
| [NextMethod 함수](nextmethod.md) | 열거형의 다음 메서드를 검색합니다. |
| [Put 함수](put.md) | 명명된 된 속성을 새 값으로 설정합니다. |
| [PutClassWmi 함수](putclasswmi.md) | 새 클래스를 만들거나 기존을 업데이트 합니다. |
| [PutInstanceWmi 함수](putinstancewmi.md) | 만들거나 기존 클래스의 인스턴스를 업데이트 합니다. 인스턴스는 WMI 리포지토리에 기록 됩니다. |
| [PutMethod 함수](putmethod.md) | 메서드를 만듭니다. |
| [QualifierSet_BeginEnumeration 함수](qualifierset-beginenumeration.md) | 열거형의 시작 부분에 있는 개체의 한정자의 열거자를 다시 설정합니다. |
| [QualifierSet_Delete 함수](qualifierset-delete.md) | 이름으로 지정된 된 한정자를 삭제합니다.  |
| [QualifierSet_EndEnumeration 함수](qualifierset-endenumeration.md) | 열거형에 대 한 호출을 시작한 종료는 `QualifierSet_BeginEnumeration` 함수입니다. |
| [QualifierSet_Get 함수](qualifierset-get.md) | 지정된 된 명명 된 한정자를 가져옵니다.  |
| [QualifierSet_GetNames 함수](qualifierset-getnames.md) | 현재 개체 또는 속성에서 사용할 수 있는 지정 된 한정자 또는 모든 한정자의 이름을 검색 합니다. |
| [QualifierSet_Next 함수](qualifierset-next.md) | 다음 한정자에 대 한 호출을 시작 하는 열거형에는 검색 된 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다. |
| [QualifierSet_Put 함수](qualifierset-put.md) | 명명 된 한정자 및 값을 씁니다. |
| [ResetSecurity 함수](resetsecurity.md) | 현재 스레드의에 제공 된 가장 토큰을 지정합니다. |
| [SetSecurity 함수](setsecurity.md) | 현재 스레드와 연결 된 가장 토큰을 검색 합니다. |
| [SpawnDerivedClass 함수](spawnderivedclass.md) | 지정된 된 개체에서 새로 파생된 클래스 개체를 만듭니다. | 
| [SpawnInstance 함수](spawninstance.md) | 클래스의 새 인스턴스를 만듭니다. |   
| [VerifyClient 함수](verifyclientkey.md) | 클라이언트 키에 올바른 보안 있는지 확인 합니다. |
| [WritePropertyValue 함수](writepropertyvalue.md) | 속성 핸들에 의해 식별 된 속성에 지정된 된 수의 바이트를 씁니다. |

 ## <a name="see-also"></a>참고자료
[관리 되지 않는 API 참조](../index.md) 
