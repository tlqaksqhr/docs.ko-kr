---
title: "방법: UI인 추가 기능 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI인 추가 기능 만들기[WPF]"
  - "추가 기능 [WPF] UI"
  - "UI 추가 기능 만들기[WPF]"
  - "UI 추가 기능 [WPF], 만들기"
  - "UI 추가 기능 구현[WPF]"
  - "추가 기능을 만들어 파이프라인 세그먼트 [WPF]"
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: UI인 추가 기능 만들기
\<?xml version="1.0" encoding="utf-8"?>
\<developerHowToDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>이 예제에는 추가 기능에 만드는 방법을 보여 줍니다는 <token>TLA #tla_wpf</token> <token>TLA #tla_ui</token> 에서 호스팅되는 <token>TLA&#2;tla_wpf</token> 독립 실행형 응용 프로그램.</para> 
    <para>은 추가 기능에 <token>TLA&#2;tla_ui</token> 즉는 <token>TLA&#2;tla_wpf</token> 사용자 정의 컨트롤입니다. 사용자 정의 컨트롤의 콘텐츠는 단일 단추를 클릭 하면 그 메시지 상자를 표시 합니다. <token>TLA&#2;tla_wpf</token> 추가 기능에서 독립 실행형 응용 프로그램을 호스트 <token>TLA&#2;tla_ui</token> 기본 응용 프로그램 창의 콘텐츠로.</para> 
    <para> 
      <embeddedLabel>필수 구성 요소</embeddedLabel>
    </para>
    <para>이 예제에서는 강조는 <token>TLA&#2;tla_wpf</token> 에 대 한 확장은 <token>dnprdnshort</token> 이 시나리오를 사용 하 고 다음을 가정 하는 추가 기능 모델:</para>
    <list class="bullet">
      <listItem>
        <para>의 기술은 <token>dnprdnshort</token> 추가 기능 모델, 파이프라인, 추가 기능 및 호스트 개발을 포함 합니다. 이러한 개념을 잘 알고 있지 않다면 참조 \<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">추가 기능 및 확장성</legacyLink>합니다. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명 하는 자습서를 참조 하십시오. \<legacyLink xlink:href="694a33c5-a040-450d-aed5-ac49fc88ce61">연습: 확장 가능한 응용 프로그램을 만드는</legacyLink>.</para> 
      </listItem> 
      <listItem> 
        <para>지식의 <token>TLA&#2;tla_wpf</token> 에 대 한 확장은 <token>dnprdnshort</token> 추가 기능에서 모델을 찾아볼 수 있습니다: \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">WPF 추가 기능 개요</link>.</para> 
      </listItem> 
    </list> 
  </introduction> 
  <codeExample> 
    <legacy> 
      <content> 
        <para>하는 추가 기능을 만들기에 <token>TLA&#2;tla_wpf</token> <token>TLA&#2;tla_ui</token> 각 파이프라인 세그먼트에서 추가 기능을 하 고 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.</para> 
        <para> 
          <token>autoOutline</token>
        </para>
      </content>
      <sections>
        <section address="Contract">
          <title>계약 파이프라인 세그먼트 구현</title>
          <content>
            <para>추가 기능인 경우는 <token>TLA&#2;tla_ui</token>, 추가 기능에 대 한 계약을 구현 해야 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>합니다. 예제에서는 <codeInline>IWPFAddInContract</codeInline> 구현 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>다음 코드에서와 같이 합니다.</para>
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInContractAttribute

namespace Contracts
{
    /// &lt;summary&gt;
    /// Defines the services that an add-in will provide to a host application.
    /// In this case, the add-in is a UI.
    /// &lt;/summary&gt;
    [AddInContract]
    public interface IWPFAddInContract : INativeHandleContract {}
}</code>
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInContractAttribute

Namespace Contracts
    ''' &lt;summary&gt;
    ''' Defines the services that an add-in will provide to a host application.
    ''' In this case, the add-in is a UI.
    ''' &lt;/summary&gt;
    &lt;AddInContract&gt;
    Public Interface IWPFAddInContract
        Inherits INativeHandleContract
        Inherits IContract
    End Interface
End Namespace</code></content>
        </section>
        <section address="AddInViewPipeline">
          <title>추가 기능 뷰 파이프라인 세그먼트 구현</title>
          <content>
            <para>추가 기능에서 하위 클래스로 구현 되기 때문에 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 을 수행 해야 하위 클래스 유형, 추가 기능 뷰 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference>합니다. 다음 코드에서는로 구현 된 계약의 추가 기능 뷰는 <codeInline>WPFAddInView</codeInline> 클래스</para> 
            <code language="c#">using System.AddIn.Pipeline; // AddInBaseAttribute
using System.Windows.Controls; // UserControl

namespace AddInViews
{
    /// &lt;summary&gt;
    /// Defines the add-in's view of the contract.
    /// &lt;/summary&gt;
    [AddInBase]
    public class WPFAddInView : UserControl { }
}</code> 
          <code language="vb">Imports System.AddIn.Pipeline ' AddInBaseAttribute
Imports System.Windows.Controls ' UserControl

Namespace AddInViews
    ''' &lt;summary&gt;
    ''' Defines the add-in's view of the contract.
    ''' &lt;/summary&gt;
    &lt;AddInBase&gt;
    Public Class WPFAddInView
        Inherits UserControl
    End Class
End Namespace</code> 
            <para>추가 기능 뷰에서 파생 되는 여기에서 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference>합니다. 따라서 추가 기능에서 <token>TLA&#2;tla_ui</token> 에서 파생 해야 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference>합니다.</para>
          </content>
        </section>
        <section address="AddInSideAdapter">
          <title>Add-In-Side 어댑터 파이프라인 세그먼트 구현</title>
          <content>
            <para>계약은 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, 추가 기능에 한 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> (추가 기능 뷰 파이프라인 세그먼트에 의해 지정 된 대로). 따라서는 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 으로 변환 해야는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 격리 경계를 통과 하기 전에 합니다. 이 작업은 호출 하 여 추가 기능 측 어댑터에 의해 수행 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>다음 코드에 표시 된 것 처럼.</para> 
            <code language="c#">using System; // IntPtr
using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
using System.Security.Permissions;

using AddInViews; // WPFAddInView
using Contracts; // IWPFAddInContract

namespace AddInSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in's view of the contract to the add-in contract
    /// &lt;/summary&gt;
    [AddInAdapter]
    public class WPFAddIn_ViewToContractAddInSideAdapter : ContractBase, IWPFAddInContract
    {
        WPFAddInView wpfAddInView;

        public WPFAddIn_ViewToContractAddInSideAdapter(WPFAddInView wpfAddInView)
        {
            // Adapt the add-in view of the contract (WPFAddInView) 
            // to the contract (IWPFAddInContract)
            this.wpfAddInView = wpfAddInView;
        }

        /// &lt;summary&gt;
        /// ContractBase.QueryContract must be overridden to:
        /// * Safely return a window handle for an add-in UI to the host 
        ///   application's application.
        /// * Enable tabbing between host application UI and add-in UI, in the
        ///   "add-in is a UI" scenario.
        /// &lt;/summary&gt;
        public override IContract QueryContract(string contractIdentifier)
        {
            if (contractIdentifier.Equals(typeof(INativeHandleContract).AssemblyQualifiedName))
            {
                return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView);
            }

            return base.QueryContract(contractIdentifier);
        }

        /// &lt;summary&gt;
        /// GetHandle is called by the WPF add-in model from the host application's 
        /// application domain to to get the window handle for an add-in UI from the 
        /// add-in's application domain. GetHandle is called if a window handle isn't 
        /// returned by other means ie overriding ContractBase.QueryContract, 
        /// as shown above.
        /// NOTE: This method requires UnmanagedCodePermission to be called 
        ///       (full-trust by default), to prevent illegal window handle
        ///       access in partially trusted scenarios. If the add-in could
        ///       run in a partially trusted application domain 
        ///       (eg AddInSecurityLevel.Internet), you can safely return a window
        ///       handle by overriding ContractBase.QueryContract, as shown above.
        /// &lt;/summary&gt;
        [SecurityPermissionAttribute(SecurityAction.Demand, Flags = SecurityPermissionFlag.UnmanagedCode)]
        public IntPtr GetHandle()
        {
            return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView).GetHandle();
        }
    }
}</code> 
          <code language="vb">Imports System ' IntPtr
Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
Imports System.Security.Permissions

Imports AddInViews ' WPFAddInView
Imports Contracts ' IWPFAddInContract

Namespace AddInSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in's view of the contract to the add-in contract
    ''' &lt;/summary&gt;
    &lt;AddInAdapter&gt;
    Public Class WPFAddIn_ViewToContractAddInSideAdapter
        Inherits ContractBase
        Implements IWPFAddInContract

        Private wpfAddInView As WPFAddInView

        Public Sub New(ByVal wpfAddInView As WPFAddInView)
            ' Adapt the add-in view of the contract (WPFAddInView) 
            ' to the contract (IWPFAddInContract)
            Me.wpfAddInView = wpfAddInView
        End Sub

        ''' &lt;summary&gt;
        ''' ContractBase.QueryContract must be overridden to:
        ''' * Safely return a window handle for an add-in UI to the host 
        '''   application's application.
        ''' * Enable tabbing between host application UI and add-in UI, in the
        '''   "add-in is a UI" scenario.
        ''' &lt;/summary&gt;
        Public Overrides Function QueryContract(ByVal contractIdentifier As String) As IContract
            If contractIdentifier.Equals(GetType(INativeHandleContract).AssemblyQualifiedName) Then
                Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView)
            End If

            Return MyBase.QueryContract(contractIdentifier)
        End Function

        ''' &lt;summary&gt;
        ''' GetHandle is called by the WPF add-in model from the host application's 
        ''' application domain to to get the window handle for an add-in UI from the 
        ''' add-in's application domain. GetHandle is called if a window handle isn't 
        ''' returned by other means ie overriding ContractBase.QueryContract, 
        ''' as shown above.
        ''' NOTE: This method requires UnmanagedCodePermission to be called 
        '''       (full-trust by default), to prevent illegal window handle
        '''       access in partially trusted scenarios. If the add-in could
        '''       run in a partially trusted application domain 
        '''       (eg AddInSecurityLevel.Internet), you can safely return a window
        '''       handle by overriding ContractBase.QueryContract, as shown above.
        ''' &lt;/summary&gt;
        &lt;SecurityPermissionAttribute(SecurityAction.Demand, Flags:=SecurityPermissionFlag.UnmanagedCode)&gt;
        Public Function GetHandle() As IntPtr Implements INativeHandleContract.GetHandle
            Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView).GetHandle()
        End Function

    End Class
End Namespace</code> 
            <para>추가 기능 모델은 추가 기능에서 반환 하는 위치에 <token>TLA&#2;tla_ui</token> (참조 \<link xlink:href="57f274b7-4c66-4b72-92eb-81939a393776">하는 방법: UI는 추가 기능에 반환 되도록 만듭니다</link>), 변환 하는 추가 기능 어댑터는 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 에 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 를 호출 하 여 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>합니다. <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> 도 호출 해야이 모델에서를 호출 하는 코드를 작성 하는 메서드를 구현 해야 합니다. 재정의 하 여이 작업을 수행 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> 호출 하는 코드를 구현 하 고 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> 경우 호출 하는 코드 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> 예상는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>합니다. 이 경우 호출자에 게 호스트 측 어댑터는 다음 하위 섹션에서 설명 됩니다.</para>
            <alert class="note">
              <para> 재정의 해야 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> 호스트 응용 프로그램 간 탭 이동 사용 하도록 설정 하려면이 모델에서 <token>TLA&#2;tla_ui</token> 및 추가 기능 <token>TLA&#2;tla_ui</token>합니다. 자세한 내용은 "WPF 추가 기능에 제한 사항"의 참조 \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">WPF 추가 기능 개요</link>.</para> 
            </alert> 
            <para>추가 기능 측 어댑터에서 파생 되는 인터페이스를 구현 하기 때문에 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>를 구현 해야 <codeEntityReference autoUpgrade="true">M:System.AddIn.Contract.INativeHandleContract.GetHandle</codeEntityReference>메시지를 무시 하지만 때 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> 재정의 됩니다.</para>
          </content>
        </section>
        <section address="HostViewPipeline">
          <title>호스트 뷰 파이프라인 세그먼트 구현</title>
          <content>
            <para>이 모델에서는 호스트 응용 프로그램은 일반적으로 예상 호스트 뷰를는 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 하위 클래스입니다. 호스트 측 어댑터 변환 해야는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 에 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 후는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 격리 경계를 통과 합니다. 호스트 응용 프로그램을 가져오는 메서드를 호출 하지 때문에 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference>, 호스트 뷰를 반환 해야 합니다""는 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 포함 하 여 합니다. 호스트 보기의 하위 클래스에서 파생 되어야 따라서 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 기타를 포함할 수 있는 <token>TLA&#2;tla_ui #plural</token>와 같은 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference>합니다. 다음 코드에서는로 구현 된 계약의 호스트 뷰는 <codeInline>같이</codeInline> 클래스입니다.</para>
            <code language="c#">using System.Windows.Controls; // UserControl

namespace HostViews
{
    /// &lt;summary&gt;
    /// Defines the host's view of the add-in
    /// &lt;/summary&gt;
    public class WPFAddInHostView : UserControl { }
}</code>
          <code language="vb">Imports System.Windows.Controls ' UserControl

Namespace HostViews
    ''' &lt;summary&gt;
    ''' Defines the host's view of the add-in
    ''' &lt;/summary&gt;
    Public Class WPFAddInHostView
        Inherits UserControl
    End Class
End Namespace</code>
          </content>
        </section>
        <section address="HostSideAdapter">
          <title>호스트 측 어댑터 파이프라인 세그먼트 구현</title>
          <content>
            <para>계약은 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference>, 호스트 응용 프로그램은 예상 된 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference> ([호스트] 보기에서 지정 된 대로). 따라서는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 으로 변환 해야는 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 호스트 보기의 내용으로 설정 하기 전에 격리 경계를 통과 한 후 (에서 파생 된 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference>).</para> 
            <para>다음 코드와 같이이 작업 호스트 측 어댑터에 의해 수행 됩니다. </para> 
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
using System.Windows; // FrameworkElement

using Contracts; // IWPFAddInContract
using HostViews; // WPFAddInHostView

namespace HostSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in contract to the host's view of the add-in
    /// &lt;/summary&gt;
    [HostAdapter]
    public class WPFAddIn_ContractToViewHostSideAdapter : WPFAddInHostView
    {
        IWPFAddInContract wpfAddInContract;
        ContractHandle wpfAddInContractHandle;

        public WPFAddIn_ContractToViewHostSideAdapter(IWPFAddInContract wpfAddInContract)
        {
            // Adapt the contract (IWPFAddInContract) to the host application's
            // view of the contract (WPFAddInHostView)
            this.wpfAddInContract = wpfAddInContract;

            // Prevent the reference to the contract from being released while the
            // host application uses the add-in
            this.wpfAddInContractHandle = new ContractHandle(wpfAddInContract);

            // Convert the INativeHandleContract for the add-in UI that was passed 
            // from the add-in side of the isolation boundary to a FrameworkElement
            string aqn = typeof(INativeHandleContract).AssemblyQualifiedName;
            INativeHandleContract inhc = (INativeHandleContract)wpfAddInContract.QueryContract(aqn);
            FrameworkElement fe = (FrameworkElement)FrameworkElementAdapters.ContractToViewAdapter(inhc);

            // Add FrameworkElement (which displays the UI provided by the add-in) as
            // content of the view (a UserControl)
            this.Content = fe;
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
Imports System.Windows ' FrameworkElement

Imports Contracts ' IWPFAddInContract
Imports HostViews ' WPFAddInHostView

Namespace HostSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in contract to the host's view of the add-in
    ''' &lt;/summary&gt;
    &lt;HostAdapter&gt;
    Public Class WPFAddIn_ContractToViewHostSideAdapter
        Inherits WPFAddInHostView
        Private wpfAddInContract As IWPFAddInContract
        Private wpfAddInContractHandle As ContractHandle

        Public Sub New(ByVal wpfAddInContract As IWPFAddInContract)
            ' Adapt the contract (IWPFAddInContract) to the host application's
            ' view of the contract (WPFAddInHostView)
            Me.wpfAddInContract = wpfAddInContract

            ' Prevent the reference to the contract from being released while the
            ' host application uses the add-in
            Me.wpfAddInContractHandle = New ContractHandle(wpfAddInContract)

            ' Convert the INativeHandleContract for the add-in UI that was passed 
            ' from the add-in side of the isolation boundary to a FrameworkElement
            Dim aqn As String = GetType(INativeHandleContract).AssemblyQualifiedName
            Dim inhc As INativeHandleContract = CType(wpfAddInContract.QueryContract(aqn), INativeHandleContract)
            Dim fe As FrameworkElement = CType(FrameworkElementAdapters.ContractToViewAdapter(inhc), FrameworkElement)

            ' Add FrameworkElement (which displays the UI provided by the add-in) as
            ' content of the view (a UserControl)
            Me.Content = fe
        End Sub
    End Class
End Namespace</code> 
            <para>호스트 측 어댑터 획득 볼 수 있듯이 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 추가 기능 측 어댑터를 호출 하 여 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.ContractBase.QueryContract(System.String)</codeEntityReference> 메서드 (지점 위치는 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 격리 경계를 통과).</para> 
            <para>호스트 측 어댑터 그런 다음 변환의 <codeEntityReference autoUpgrade="true">T:System.AddIn.Contract.INativeHandleContract</codeEntityReference> 에 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> 를 호출 하 여 <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter(System.AddIn.Contract.INativeHandleContract)</codeEntityReference>합니다. 마지막으로 <codeEntityReference autoUpgrade="true">클래스로</codeEntityReference> [호스트] 보기의 내용으로 설정 됩니다.</para>
          </content>
        </section>
        <section address="AddIn">
          <title>추가 기능을 구현</title>
          <content>
            <para>추가 기능 측 어댑터와 위치에 추가 기능 뷰 추가 기능을 구현할 수 있습니다 추가 기능 뷰에서 파생 하 여 다음 코드에 나와 있는 것 처럼.</para> 
            <code language="xaml">&lt;addInViews:WPFAddInView
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:addInViews="clr-namespace:AddInViews;assembly=AddInViews"
    x:Class="WPFAddIn1.AddInUI"&gt;

    &lt;Grid&gt;
        &lt;Button Click="clickMeButton_Click" Content="Click Me!" /&gt;        
    &lt;/Grid&gt;

&lt;/addInViews:WPFAddInView&gt;</code> 
            <code language="c#">using System.AddIn; // AddInAttribute
using System.Windows; // MessageBox, RoutedEventArgs

using AddInViews; // WPFAddInView

namespace WPFAddIn1
{
    /// &lt;summary&gt;
    /// Implements the add-in by deriving from WPFAddInView
    /// &lt;/summary&gt;
    [AddIn("WPF Add-In 1")]
    public partial class AddInUI : WPFAddInView
    {
        public AddInUI()
        {
            InitializeComponent();
        }

        void clickMeButton_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Hello from WPFAddIn1");
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn ' AddInAttribute
Imports System.Windows ' MessageBox, RoutedEventArgs

Imports AddInViews ' WPFAddInView

Namespace WPFAddIn1
    ''' &lt;summary&gt;
    ''' Implements the add-in by deriving from WPFAddInView
    ''' &lt;/summary&gt;
    &lt;AddIn("WPF Add-In 1")&gt;
    Partial Public Class AddInUI
        Inherits WPFAddInView
        Public Sub New()
            InitializeComponent()
        End Sub

        Private Sub clickMeButton_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
            MessageBox.Show("Hello from WPFAddIn1")
        End Sub
    End Class
End Namespace</code> 
            <para>이 예제에서이 모델의 흥미로운 이점 중 하나를 볼 수 있습니다: 추가 기능 개발자만 추가 기능을 구현 해야 할 (이므로 <token>TLA&#2;tla_ui</token> 도), 추가 기능 클래스 및 추가 기능에 대신 <token>TLA&#2;tla_ui</token>합니다.</para>
          </content>
        </section>
        <section address="HostApp">
          <title>호스트 응용 프로그램을 구현</title>
          <content>
            <para>호스트 측 어댑터와 호스트 뷰를 만든 호스트 응용 프로그램이 사용할 수는 <token>dnprdnshort</token> 파이프라인을 열고 추가 기능의 호스트 뷰를 가져올 추가 기능 모델입니다. 이러한 단계는 다음 코드에 나와 있습니다. </para> 
            <code language="c#">// Get add-in pipeline folder (the folder in which this application was launched from)
string appPath = Environment.CurrentDirectory;

// Rebuild visual add-in pipeline
string[] warnings = AddInStore.Rebuild(appPath);
if (warnings.Length &gt; 0)
{
    string msg = "Could not rebuild pipeline:";
    foreach (string warning in warnings) msg += "\n" + warning;
    MessageBox.Show(msg);
    return;
}

// Activate add-in with Internet zone security isolation
Collection&lt;AddInToken&gt; addInTokens = AddInStore.FindAddIns(typeof(WPFAddInHostView), appPath);
AddInToken wpfAddInToken = addInTokens[0];
this.wpfAddInHostView = wpfAddInToken.Activate&lt;WPFAddInHostView&gt;(AddInSecurityLevel.Internet);

// Display add-in UI
this.addInUIHostGrid.Children.Add(this.wpfAddInHostView);</code> 
          <code language="vb">' Get add-in pipeline folder (the folder in which this application was launched from)
Dim appPath As String = Environment.CurrentDirectory

' Rebuild visual add-in pipeline
Dim warnings() As String = AddInStore.Rebuild(appPath)
If warnings.Length &gt; 0 Then
    Dim msg As String = "Could not rebuild pipeline:"
    For Each warning As String In warnings
        msg &amp;= vbLf &amp; warning
    Next warning
    MessageBox.Show(msg)
    Return
End If

' Activate add-in with Internet zone security isolation
Dim addInTokens As Collection(Of AddInToken) = AddInStore.FindAddIns(GetType(WPFAddInHostView), appPath)
Dim wpfAddInToken As AddInToken = addInTokens(0)
Me.wpfAddInHostView = wpfAddInToken.Activate(Of WPFAddInHostView)(AddInSecurityLevel.Internet)

' Display add-in UI
Me.addInUIHostGrid.Children.Add(Me.wpfAddInHostView)</code> 
            <para>호스트 응용 프로그램에서 일반적인 <token>dnprdnshort</token> 는 추가 기능 활성화, 암시적으로 호스트 응용 프로그램 호스트 뷰를 반환 하는 추가 기능 모델 코드입니다. 호스트 뷰를 이후에 표시 하는 호스트 응용 프로그램 (되는 <codeEntityReference autoUpgrade="true">앞서</codeEntityReference>)에서 <codeEntityReference autoUpgrade="true">상자</codeEntityReference>.</para> 
            <para>추가와 상호 작용을 처리 하기 위한 코드 <token>TLA&#2;tla_ui</token> 추가 기능의 응용 프로그램 도메인에서 실행 합니다. 이러한 상호 작용은 다음과 같습니다:</para>
            <list class="bullet">
              <listItem>
                <para>처리는 <codeEntityReference autoUpgrade="true">눌러져</codeEntityReference> <codeEntityReference autoUpgrade="true">소스로</codeEntityReference> 이벤트.</para> 
              </listItem> 
              <listItem> 
                <para>표시는 <codeEntityReference autoUpgrade="true">T:System.Windows.MessageBox</codeEntityReference>.</para> 
              </listItem> 
            </list> 
            <para>이 활동은 호스트 응용 프로그램에서 완전히 격리 합니다.</para>
          </content>
        </section>
      </sections>
    </legacy>
  </codeExample>
  <relatedTopics>
\<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">추가 기능 및 확장성</legacyLink>
\<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">WPF 추가 기능 개요</link>
</relatedTopics>
</developerHowToDocument>
