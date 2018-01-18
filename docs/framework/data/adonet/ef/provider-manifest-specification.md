---
title: "공급자 매니페스트 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e478f145511266a919b1bc948e3218b60f3de993
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="82b89-102">공급자 매니페스트 지정</span><span class="sxs-lookup"><span data-stu-id="82b89-102">Provider Manifest Specification</span></span>
<span data-ttu-id="82b89-103">이 단원에서는 데이터 저장소 공급자가 데이터 저장소의 형식 및 함수를 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="82b89-104">엔터티 서비스는 특정 데이터 저장소 공급자와 독립적으로 작동하지만 모델, 매핑 및 쿼리가 기본 데이터 저장소와 상호 작용하는 방식을 데이터 공급자가 명시적으로 정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="82b89-105">추상 계층이 없는 경우 엔터티 서비스는 특정 데이터 저장소 또는 데이터 공급자에서만 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="82b89-106">공급자가 지원하는 형식은 기본 데이터베이스에서 직접 또는 간접적으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="82b89-107">이러한 형식은 정확한 저장소 형식일 필요는 없으며 공급자가 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 지원하기 위해 사용하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-107">These types are not necessarily the exact store types, but the types the provider uses to support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="82b89-108">공급자/저장소 형식은 EDM(엔터티 데이터 모델) 측면에서 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="82b89-109">데이터 저장소에서 지원되는 함수의 매개 변수 및 반환 형식은 EDM 측면에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82b89-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82b89-110">Requirements</span></span>  
 <span data-ttu-id="82b89-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 및 데이터 저장소는 데이터 손실이나 잘림 없이 알려진 형식으로 데이터를 전달하고 받을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-111">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="82b89-112">공급자 매니페스트는 데이터 저장소에 대한 연결을 열 필요 없이 디자인 타임에 도구를 통해 로드할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="82b89-113">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 가 대/소문자 구분, 하지만 기본 데이터 저장소 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-113">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="82b89-114">EDM 아티팩트(식별자, 형식 이름 등)가 매니페스트에서 정의되고 사용되는 경우 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 대/소문자 구분을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] case sensitivity.</span></span> <span data-ttu-id="82b89-115">대/소문자를 구분할 수 있는 데이터 저장소 요소가 공급자 매니페스트에 나타나는 경우 해당 대/소문자 구분이 공급자 매니페스트에서 유지 관리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="82b89-116">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 모든 데이터 공급자에 대한 공급자 매니페스트를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-116">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requires a provider manifest for all data providers.</span></span> <span data-ttu-id="82b89-117">공급자가 없는 공급자를 사용 하려는 경우와 매니페스트는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-117">If you try to use a provider that does not have a provider manifest with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you will get an error.</span></span>  
  
 <span data-ttu-id="82b89-118">다음 표에서는 공급자 상호 작용을 통해 예외가 발생하는 경우 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서 throw되는 예외의 종류에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-118">The following table describes the kinds of exceptions the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="82b89-119">문제</span><span class="sxs-lookup"><span data-stu-id="82b89-119">Issue</span></span>|<span data-ttu-id="82b89-120">예외</span><span class="sxs-lookup"><span data-stu-id="82b89-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="82b89-121">공급자가 DbProviderServices의 GetProviderManifest를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="82b89-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="82b89-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="82b89-123">공급자 매니페스트가 없습니다. 공급자 매니페스트를 검색하려고 할 때 공급자가 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="82b89-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="82b89-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="82b89-125">공급자 매니페스트가 잘못되었습니다. 공급자 매니페스트를 검색하려고 할 때 공급자가 잘못된 XML을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="82b89-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="82b89-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="82b89-127">시나리오</span><span class="sxs-lookup"><span data-stu-id="82b89-127">Scenarios</span></span>  
 <span data-ttu-id="82b89-128">공급자는 다음 시나리오를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="82b89-129">대칭 형식 매핑을 사용하여 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="82b89-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="82b89-130">에 대 한 공급자를 작성할 수 있습니다는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 각 저장소 형식이 매핑됩니다 매핑 방향에 관계 없이 단일 EDM 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-130">You can write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="82b89-131">EDM 형식에 해당하는 가장 단순한 매핑이 있는 공급자 형식의 경우 형식 시스템이 단순하거나 EDM 형식과 일치하기 때문에 대칭 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="82b89-132">해당 도메인의 단순성을 사용하고 정적 선언적 공급자 매니페스트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="82b89-133">다음 두 섹션이 있는 XML 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-133">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="82b89-134">저장소 형식 또는 함수의 "해당하는 EDM 항목" 측면에서 표현된 공급자 형식의 목록.</span><span class="sxs-lookup"><span data-stu-id="82b89-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="82b89-135">저장소 형식에는 해당하는 EDM 형식이 있고,</span><span class="sxs-lookup"><span data-stu-id="82b89-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="82b89-136">저장소 함수에는 해당하는 EDM 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="82b89-137">예를 들어, varchar은 SQL Server 형식이지만 해당하는 EDM 형식은 string입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
-   <span data-ttu-id="82b89-138">매개 변수와 반환 형식이 EDM 측면에서 표현된, 공급자가 지원하는 함수의 목록</span><span class="sxs-lookup"><span data-stu-id="82b89-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="82b89-139">비대칭 형식 매핑을 사용하여 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="82b89-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="82b89-140">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에 대한 데이터 저장소 공급자를 작성하는 경우 일부 형식에 대한 EDM-공급자 형식 매핑은 공급자-EDM 형식 매핑과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-140">When writing a data store provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="82b89-141">예를 들어, 바인딩되지 않은 EDM PrimitiveTypeKind.String은 공급자에서 nvarchar(4000)에 매핑될 수 있지만 nvarchar(4000)은 EDM PrimitiveTypeKind.String(MaxLength=4000)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="82b89-142">다음 두 섹션이 있는 XML 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-142">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="82b89-143">EDM 측면에서 표현되고 양방향(EDM-공급자 및 공급자-EDM)의 매핑을 정의하는 공급자 형식의 목록</span><span class="sxs-lookup"><span data-stu-id="82b89-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
-   <span data-ttu-id="82b89-144">매개 변수와 반환 형식이 EDM 측면에서 표현된, 공급자가 지원하는 함수의 목록</span><span class="sxs-lookup"><span data-stu-id="82b89-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="82b89-145">공급자 매니페스트 검색 기능</span><span class="sxs-lookup"><span data-stu-id="82b89-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="82b89-146">매니페스트는 엔터티 서비스의 몇 가지 구성 요소 형식(도구 또는 쿼리 등)에서 간접적으로 사용되지만 데이터 저장소 메타데이터 로더의 사용을 통해 메타데이터에서 보다 직접적으로 활용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="82b89-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="82b89-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="82b89-148">그러나 지정된 공급자가 여러 저장소나 여러 버전의 동일한 저장소를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="82b89-149">따라서 공급자는 지원되는 데이터 저장소마다 다른 매니페스트를 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="82b89-150">공급자 매니페스트 토큰</span><span class="sxs-lookup"><span data-stu-id="82b89-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="82b89-151">데이터 저장소 연결이 열린 경우 공급자가 올바른 매니페스트를 반환하기 위해 정보를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="82b89-152">이는 연결 정보를 사용할 수 없거나 저장소에 연결할 수 없는 오프라인 시나리오에서는 가능하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="82b89-153">.ssdl 파일에서 `ProviderManifestToken` 요소의 `Schema` 특성을 사용하여 매니페스트를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="82b89-154">이 특성에는 필수 형식이 없습니다. 공급자는 저장소에 대한 연결을 열지 않고 매니페스트를 식별하는 데 필요한 최소한의 정보를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="82b89-155">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="82b89-156">공급자 매니페스트 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="82b89-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="82b89-157">공급자는 <xref:System.Data.Common.DbXmlEnabledProviderManifest>에서 파생되므로 매니페스트를 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="82b89-158">다음 그림에서는 공급자의 클래스 계층 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="82b89-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="82b89-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="82b89-160">검색 기능 API</span><span class="sxs-lookup"><span data-stu-id="82b89-160">Discoverability API</span></span>  
 <span data-ttu-id="82b89-161">공급자 매니페스트는 데이터 저장소 연결이나 공급자 매니페스트 토큰을 사용하여 저장소 메타데이터 로더(StoreItemCollection)에 의해 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="82b89-162">데이터 저장소 연결 사용</span><span class="sxs-lookup"><span data-stu-id="82b89-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="82b89-163">데이터 저장소 연결을 사용할 수 있는 경우 DbProvderServices.GetProviderManifestToken을 호출하여 GetProviderManifest 메서드에 전달되는 토큰을 반환합니다. GetProviderManifest 메서드는 DbProviderManifest를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-163">When the data store connection is available, call DbProvderServices.GetProviderManifestToken to return the token that is passed to the GetProviderManifest method, which returns DbProviderManifest.</span></span> <span data-ttu-id="82b89-164">이 메서드는 공급자의 GetDbProviderManifestToken 구현에 작업을 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-164">This method delegates to the provider's implementation of GetDbProviderManifestToken.</span></span>  
  
```  
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="82b89-165">공급자 매니페스트 토큰 사용</span><span class="sxs-lookup"><span data-stu-id="82b89-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="82b89-166">오프라인 시나리오의 경우 토큰이 SSDL 표현에서 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="82b89-167">SSDL을 사용 하면 한 ProviderManifestToken를 지정할 수 있습니다 (참조 [스키마 요소 (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222) 자세한 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="82b89-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222) for more information).</span></span> <span data-ttu-id="82b89-168">예를 들어, 연결을 열 수 없는 경우 SSDL에는 매니페스트에 대한 정보를 지정하는 공급자 매니페스트 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="82b89-169">공급자 매니페스트 스키마</span><span class="sxs-lookup"><span data-stu-id="82b89-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="82b89-170">각 공급자에 대해 정의된 정보의 스키마에는 메타데이터에서 사용할 정적 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="82b89-171">Types 노드</span><span class="sxs-lookup"><span data-stu-id="82b89-171">Types Node</span></span>  
 <span data-ttu-id="82b89-172">공급자 매니페스트의 Types 노드에는 공급자를 통해서나 데이터 저장소에서 기본적으로 지원하는 형식에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="82b89-173">Type 노드</span><span class="sxs-lookup"><span data-stu-id="82b89-173">Type Node</span></span>  
 <span data-ttu-id="82b89-174">각 Type 노드는 EDM 측면에서 공급자 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="82b89-175">Type 노드는 공급자 형식의 이름, 매핑하는 모델 형식과 관련된 정보 및 해당 형식 매핑을 설명하기 위한 패싯을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="82b89-176">공급자 매니페스트에서 이 형식 정보를 표현하기 위해 각 TypeInformation 선언은 각 형식에 대한 몇 가지 패싯 설명을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="82b89-177">특성 이름</span><span class="sxs-lookup"><span data-stu-id="82b89-177">Attribute Name</span></span>|<span data-ttu-id="82b89-178">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82b89-178">Data Type</span></span>|<span data-ttu-id="82b89-179">필수</span><span class="sxs-lookup"><span data-stu-id="82b89-179">Required</span></span>|<span data-ttu-id="82b89-180">기본값</span><span class="sxs-lookup"><span data-stu-id="82b89-180">Default Value</span></span>|<span data-ttu-id="82b89-181">설명</span><span class="sxs-lookup"><span data-stu-id="82b89-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="82b89-182">이름</span><span class="sxs-lookup"><span data-stu-id="82b89-182">Name</span></span>|<span data-ttu-id="82b89-183">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-183">String</span></span>|<span data-ttu-id="82b89-184">예</span><span class="sxs-lookup"><span data-stu-id="82b89-184">Yes</span></span>|<span data-ttu-id="82b89-185">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-185">n/a</span></span>|<span data-ttu-id="82b89-186">공급자별 데이터 형식 이름</span><span class="sxs-lookup"><span data-stu-id="82b89-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="82b89-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="82b89-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="82b89-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="82b89-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="82b89-189">예</span><span class="sxs-lookup"><span data-stu-id="82b89-189">Yes</span></span>|<span data-ttu-id="82b89-190">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-190">n/a</span></span>|<span data-ttu-id="82b89-191">EDM 형식 이름</span><span class="sxs-lookup"><span data-stu-id="82b89-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="82b89-192">Function 노드</span><span class="sxs-lookup"><span data-stu-id="82b89-192">Function Node</span></span>  
 <span data-ttu-id="82b89-193">각 Function은 공급자를 통해 사용할 수 있는 단일 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="82b89-194">특성 이름</span><span class="sxs-lookup"><span data-stu-id="82b89-194">Attribute Name</span></span>|<span data-ttu-id="82b89-195">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82b89-195">Data Type</span></span>|<span data-ttu-id="82b89-196">필수</span><span class="sxs-lookup"><span data-stu-id="82b89-196">Required</span></span>|<span data-ttu-id="82b89-197">기본값</span><span class="sxs-lookup"><span data-stu-id="82b89-197">Default Value</span></span>|<span data-ttu-id="82b89-198">설명</span><span class="sxs-lookup"><span data-stu-id="82b89-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="82b89-199">이름</span><span class="sxs-lookup"><span data-stu-id="82b89-199">Name</span></span>|<span data-ttu-id="82b89-200">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-200">String</span></span>|<span data-ttu-id="82b89-201">예</span><span class="sxs-lookup"><span data-stu-id="82b89-201">Yes</span></span>|<span data-ttu-id="82b89-202">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-202">n/a</span></span>|<span data-ttu-id="82b89-203">함수의 식별자/이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="82b89-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="82b89-204">ReturnType</span></span>|<span data-ttu-id="82b89-205">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-205">String</span></span>|<span data-ttu-id="82b89-206">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-206">No</span></span>|<span data-ttu-id="82b89-207">Void</span><span class="sxs-lookup"><span data-stu-id="82b89-207">Void</span></span>|<span data-ttu-id="82b89-208">함수의 EDM 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="82b89-209">Aggregate</span><span class="sxs-lookup"><span data-stu-id="82b89-209">Aggregate</span></span>|<span data-ttu-id="82b89-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="82b89-210">Boolean</span></span>|<span data-ttu-id="82b89-211">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-211">No</span></span>|<span data-ttu-id="82b89-212">False</span><span class="sxs-lookup"><span data-stu-id="82b89-212">False</span></span>|<span data-ttu-id="82b89-213">함수가 집계 함수인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="82b89-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="82b89-214">BuiltIn</span></span>|<span data-ttu-id="82b89-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="82b89-215">Boolean</span></span>|<span data-ttu-id="82b89-216">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-216">No</span></span>|<span data-ttu-id="82b89-217">True</span><span class="sxs-lookup"><span data-stu-id="82b89-217">True</span></span>|<span data-ttu-id="82b89-218">함수가 데이터 저장소에 기본 제공되는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="82b89-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="82b89-219">StoreFunctionName</span></span>|<span data-ttu-id="82b89-220">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-220">String</span></span>|<span data-ttu-id="82b89-221">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-221">No</span></span>|<span data-ttu-id="82b89-222">\<Name></span><span class="sxs-lookup"><span data-stu-id="82b89-222">\<Name></span></span>|<span data-ttu-id="82b89-223">데이터 저장소의 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-223">Function Name in the data store.</span></span>  <span data-ttu-id="82b89-224">함수 이름의 리디렉션 수준을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="82b89-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="82b89-225">NiladicFunction</span></span>|<span data-ttu-id="82b89-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="82b89-226">Boolean</span></span>|<span data-ttu-id="82b89-227">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-227">No</span></span>|<span data-ttu-id="82b89-228">False</span><span class="sxs-lookup"><span data-stu-id="82b89-228">False</span></span>|<span data-ttu-id="82b89-229">함수가 매개 변수를 필요로 하지 않고 매개 변수 없이 호출되는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="82b89-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="82b89-230">ParameterType</span></span><br /><br /> <span data-ttu-id="82b89-231">의미 체계</span><span class="sxs-lookup"><span data-stu-id="82b89-231">Semantics</span></span>|<span data-ttu-id="82b89-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="82b89-232">ParameterSemantics</span></span>|<span data-ttu-id="82b89-233">아니요</span><span class="sxs-lookup"><span data-stu-id="82b89-233">No</span></span>|<span data-ttu-id="82b89-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="82b89-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="82b89-235">변환</span><span class="sxs-lookup"><span data-stu-id="82b89-235">Conversion</span></span>|<span data-ttu-id="82b89-236">쿼리 파이프라인에서 매개 변수 형식 대체를 처리할 방법에 대한 선택 항목:</span><span class="sxs-lookup"><span data-stu-id="82b89-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="82b89-237">-   ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="82b89-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="82b89-238">-   AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="82b89-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="82b89-239">-   AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="82b89-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="82b89-240">**매개 변수 노드**</span><span class="sxs-lookup"><span data-stu-id="82b89-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="82b89-241">각 함수에는 하나 이상의 Parameter 노드로 구성된 컬렉션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="82b89-242">특성 이름</span><span class="sxs-lookup"><span data-stu-id="82b89-242">Attribute Name</span></span>|<span data-ttu-id="82b89-243">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82b89-243">Data Type</span></span>|<span data-ttu-id="82b89-244">필수</span><span class="sxs-lookup"><span data-stu-id="82b89-244">Required</span></span>|<span data-ttu-id="82b89-245">기본값</span><span class="sxs-lookup"><span data-stu-id="82b89-245">Default Value</span></span>|<span data-ttu-id="82b89-246">설명</span><span class="sxs-lookup"><span data-stu-id="82b89-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="82b89-247">이름</span><span class="sxs-lookup"><span data-stu-id="82b89-247">Name</span></span>|<span data-ttu-id="82b89-248">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-248">String</span></span>|<span data-ttu-id="82b89-249">예</span><span class="sxs-lookup"><span data-stu-id="82b89-249">Yes</span></span>|<span data-ttu-id="82b89-250">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-250">n/a</span></span>|<span data-ttu-id="82b89-251">매개 변수의 식별자/이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="82b89-252">형식</span><span class="sxs-lookup"><span data-stu-id="82b89-252">Type</span></span>|<span data-ttu-id="82b89-253">문자열</span><span class="sxs-lookup"><span data-stu-id="82b89-253">String</span></span>|<span data-ttu-id="82b89-254">예</span><span class="sxs-lookup"><span data-stu-id="82b89-254">Yes</span></span>|<span data-ttu-id="82b89-255">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-255">n/a</span></span>|<span data-ttu-id="82b89-256">매개 변수의 EDM 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="82b89-257">모드</span><span class="sxs-lookup"><span data-stu-id="82b89-257">Mode</span></span>|<span data-ttu-id="82b89-258">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82b89-258">Parameter</span></span><br /><br /> <span data-ttu-id="82b89-259">방향</span><span class="sxs-lookup"><span data-stu-id="82b89-259">Direction</span></span>|<span data-ttu-id="82b89-260">예</span><span class="sxs-lookup"><span data-stu-id="82b89-260">Yes</span></span>|<span data-ttu-id="82b89-261">해당 없음</span><span class="sxs-lookup"><span data-stu-id="82b89-261">n/a</span></span>|<span data-ttu-id="82b89-262">매개 변수의 방향:</span><span class="sxs-lookup"><span data-stu-id="82b89-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="82b89-263">-   in</span><span class="sxs-lookup"><span data-stu-id="82b89-263">-   in</span></span><br /><span data-ttu-id="82b89-264">-out</span><span class="sxs-lookup"><span data-stu-id="82b89-264">-   out</span></span><br /><span data-ttu-id="82b89-265">-   inout</span><span class="sxs-lookup"><span data-stu-id="82b89-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="82b89-266">Namespace 특성</span><span class="sxs-lookup"><span data-stu-id="82b89-266">Namespace Attribute</span></span>  
 <span data-ttu-id="82b89-267">각 데이터 저장소 공급자는 매니페스트에서 정의된 정보에 대한 네임스페이스 또는 네임스페이스 그룹을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="82b89-268">이 네임스페이스를 Entity SQL 쿼리에서 사용하여 함수 및 형식의 이름을 확인할 수 있습니다(예:</span><span class="sxs-lookup"><span data-stu-id="82b89-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="82b89-269">SqlServer).</span><span class="sxs-lookup"><span data-stu-id="82b89-269">For instance: SqlServer.</span></span> <span data-ttu-id="82b89-270">해당 네임스페이스는 Entity SQL 쿼리에서 표준 함수를 지원할 수 있도록 엔터티 서비스에서 정의하는 정식 네임스페이스인 EDM과 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b89-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b89-271">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82b89-271">See Also</span></span>  
 [<span data-ttu-id="82b89-272">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="82b89-272">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
