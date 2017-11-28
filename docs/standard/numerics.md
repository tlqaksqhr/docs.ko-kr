---
title: ".NET Framework의 숫자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6090f198815f1149e212c7a57b40187ded9264f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="numerics-in-the-net-framework"></a>.NET Framework의 숫자
.NET Framework에서는 표준 숫자 정수 계열 및 부동 소수점 기본 형식과 <xref:System.Numerics.BigInteger>, 이론적 상한 또는 하한이 없는 정수 형식, <xref:System.Numerics.Complex>, 복소수를 나타내는 형식, <xref:System.Numerics> 네임스페이스에서 SIMD 사용 벡터 형식 집합을 지원합니다.  
  
 또한 벡터 형식의 SIMD 사용 라이브러리인 System.Numerics.Vectors가 NuGet 패키지로 릴리스되었습니다.  
  
## <a name="integral-types"></a>정수 계열 형식 표  
 .NET Framework에서는 1~8바이트 범위 길이의 부호 있는 정수와 부호 없는 정수를 둘 다 지원합니다. 다음 표에서는 정수 계열 형식 및 해당 크기 목록을 제공하고 부호가 있는지 여부를 표시하고 해당 범위를 문서화합니다. 모든 정수는 값 형식입니다.  
  
|형식|부호 있음/부호 없음|크기(바이트)|최소값|최대값|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|부호 없음|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|서명|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=nameWithType>|서명|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=nameWithType>|서명|9|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=nameWithType>|서명|1|-128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|부호 없음|2|0|65,535|  
|<xref:System.UInt32?displayProperty=nameWithType>|부호 없음|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=nameWithType>|부호 없음|9|0|18,446,744,073,709,551,615|  
  
 각 정수 계열 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합을 지원합니다. 각 정수에는 같음 비교 및 상대 비교를 수행하고, 숫자의 문자열 표시를 해당 정수로 변환하고, 정수를 해당 문자열 표시로 변환하는 메서드가 포함됩니다. 두 정수의 더 작거나 더 큰 값을 반올림하고 식별하는 연산과 같이 표준 연산자를 통해 처리되는 연산 이외의 몇몇 추가 수치 연산은 <xref:System.Math> 클래스에서 제공됩니다. <xref:System.BitConverter> 클래스를 사용하여 정수 값의 개별 비트를 사용할 수도 있습니다.  
  
 부호 없는 정수 형식은 CLS와 호환되지 않습니다. 자세한 내용은 [언어 독립성 및 언어 독립적 구성 요소](../../docs/standard/language-independence-and-language-independent-components.md)를 참조하세요.  
  
## <a name="floating-point-types"></a>부동 소수점 형식  
 .NET Framework에는 다음 표에 나열된 세 가지 기본 형식 부동 소수점 형식이 포함됩니다.  
  
|형식|크기(바이트)|최소|Maximum|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=nameWithType>|8|-1.79769313486232e308|1.79769313486232e308|  
|<xref:System.Single?displayProperty=nameWithType>|4|-3.402823e38|3.402823e38|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|-79,228,162,514,264,337,593,543,950,335|79,228,162,514,264,337,593,543,950,335|  
  
 각 부동 소수점 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합을 지원합니다. 각 형식에는 같음 비교 및 상대 비교를 수행하고, 부동 소수점 수의 문자열 표시를 변환하고, 부동 소수점 수를 해당 문자열 표시로 변환하는 메서드가 포함됩니다. 일부 추가적인 수치, 대수 및 삼각 연산은 <xref:System.Math> 클래스에서 제공됩니다. <xref:System.BitConverter> 클래스를 사용하여 <xref:System.Double> 및 <xref:System.Single> 값의 개별 비트를 사용할 수도 있습니다. <xref:System.Decimal?displayProperty=nameWithType> 구조체에는 10진수 값의 개별 비트를 사용하기 위한 고유한 메서드인 <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> 및 <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=nameWithType>와 몇몇 추가적인 수치 연산을 수행하기 위한 고유한 메서드 집합이 있습니다.  
  
 <xref:System.Double> 및 <xref:System.Single> 형식은 기본적으로 정확하지 않은 값(태양계에서 두 별 사이의 거리) 및 정밀도가 높고 반올림 오류가 적을 필요 없는 응용 프로그램에 사용해야 합니다. 정밀도 가 더 높아야 하고 반올림 오류가 없는 것이 좋은 경우에는 <xref:System.Decimal?displayProperty=nameWithType> 형식을 사용해야 합니다.  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=nameWithType>는 이론상 값에 상한이나 하한이 없는 임의로 큰 정수를 나타내는 변경할 수 없는 형식입니다. <xref:System.Numerics.BigInteger> 형식의 메서드는 기타 정수 계열 형식의 메서드와 매우 유사합니다.  
  
## <a name="complex"></a>복합  
 <xref:System.Numerics.Complex> 형식은 실수 부분과 허수 부분이 포함된 숫자인 복소수를 나타냅니다. 이 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합과 수치, 대수 및 삼각 메서드를 지원합니다.  
  
## <a name="simd-enabled-vector-types"></a>SIMD 사용 벡터 형식  
 <xref:System.Numerics> 네임스페이스에는 .NET Framework를 위한 SIMD 사용 벡터 형식 집합이 있습니다. SIMD(Single Instruction Multiple Data) 연산을 통해 몇몇 연산은 하드웨어 수준에서 병렬 처리될 수 있습니다. 이 덕분에 벡터를 통해 계산을 수행하는 수치, 공학용 및 그래픽 앱의 성능이 크게 향상됩니다.  
  
 .NET Framework의 SIMD 사용 벡터 형식은 다음과 같습니다.  또한 System.Numerics.Vectors에는 평면 형식과 쿼터니언 형식이 있습니다.  
  
-   <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> 및 <xref:System.Numerics.Vector4> 형식은 형식 <xref:System.Single>의 2차원, 3차원 및 4차원 벡터입니다.  
  
-   두 가지 행렬 형식이 있습니다. <xref:System.Numerics.Matrix3x2>는 3x2 행렬을 나타내고 <xref:System.Numerics.Matrix4x4>는 4x4 행렬을 나타냅니다.  
  
-   <xref:System.Numerics.Plane> 및 <xref:System.Numerics.Quaternion> 형식.  
  
 SimD 사용 벡터 형식은 비SimD 사용 하드웨어 및 JIT 컴파일러에서 이 형식을 사용할 수 있는 IL에서 구현됩니다. SIMD 지침을 활용하려면 64비트 앱을 관리 코드에 대한 새로운 64비트 JIT 컴파일러로 컴파일해야 합니다. 이 관리 코드는 .NET Framework 4.6과 함께 포함되어 있으며 x64 프로세서를 대상으로 지정할 때 SIMD 지원을 추가합니다.  
  
 SIMD는 [NuGet 패키지](http://www.nuget.org/packages/System.Numerics.Vectors)로 다운로드할 수도 있습니다.  NuGet 패키지에도 포함된 제네릭 <xref:System.Numerics.Vector%601> 구조를 사용하면 기본 숫자 형식의 벡터를 만들 수 있습니다. 기본 숫자 형식에는 <xref:System.Decimal>을 제외하고 <xref:System> 네임스페이스의 모든 숫자 형식이 포함됩니다. 또한 <xref:System.Numerics.Vector%601> 구조는 벡터 작업 시 호출할 수 있는 편리한 메서드 라이브러리를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 주요 사항](../../docs/standard/application-essentials.md)
