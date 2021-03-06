# Configure BGP {#concept_ljj_4vx_dfb .concept}

You can establish Border Gateway Protocol \(BGP\) routing between a local IDC and a Virtual Border Router \(VBR\). You only need to add BGP peers that communicate with the VBR to the corresponding BGP group, and then add the BGP CIDR block to the VBR.

**Note:** Express Connect allows you to establish BGP routing only between a VBR and a local IDC. In the VBR, you must add a route entry destined for the physical connection and a route entry destined for the VPC. For more information, see [Add route entries](reseller.en-US/User Guide (New Console)/Virtual border router/Add route entries.md#).

## BGP overview {#section_e3x_wwx_dfb .section}

BGP is a dynamic routing protocol based on TCP. It is mainly used to exchange routing and network accessibility information among ASs. You can use BGP to implement intranet connection between the local IDC and VBR for physical connections. BGP can help you build hybrid clouds in a more efficient, flexible, and reliable manner.

Before configuring BGP, you need to create a BGP group. BGP groups are used to simplify BGP configurations. Combining repeated configurations into a BGP group can make configurations easier. You only need to create a BGP group according to the ASN and add qualified BGP peers to the group. The added BGP peers will inherit the configurations of the BGP group. You do not need to configure the BGP peers separately.

## Limits {#section_ksj_qxx_dfb .section}

BGP has the following limits:

-   VBR can establish BGP peers only with the peer local IDC. Static routing is still required between the VBR and the VPC.
-   The supported BGP version is BGP4.
-   VBR supports IPv4 BGP, but does not support IPv6 BGP.
-   A maximum of eight BGP peers can be created under each VBR.
-   A maximum of 100 dynamic route entries can be added to a BGP peer.
-   The Autonomous System Number \(ASN\) of Alibaba Cloud is 45104. It supports the transmission of 2-byte or 4-byte ASNs from the customer side.

## Step 1: Create a BGP Group {#section_uks_sxx_dfb .section}

Before configuring BGP routing, you need to create a BGP group based on the requested ASN.

To create a BGP group, perform the following steps:

1.  Log on to the [Express Connect](https://partners-intl.console.aliyun.com/#/ri) console.
2.  In the left-side navigation pane, click **Physical Connections** \> **Virtual Border Routers \(VBRs\)**.
3.  Select a region and click the ID of the target VBR.
4.  Click the **BGP Groups** tab, and then click **Create BGP Group**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21437/154272711012049_en-US.png)

5.  Configure the BGP group, and then click **OK**.

    |Configuration|Description|
    |:------------|:----------|
    |**Name**|Name of the BGP group|
    |**Peer ASN**|AS number of the local IDC network|
    |**BGP Key**|Key of the BGP group|
    |**Description**|Description of the BGP group|


## Step 2: Add a BGP peer {#section_lpj_tyx_dfb .section}

To add a BGP peer, perform the following steps:

1.  Log on to the [Express Connect](https://partners-intl.console.aliyun.com/#/ri) console.
2.  In the left-side navigation pane, click **Physical Connections** \> **Virtual Border Routers \(VBRs\)**.
3.  Select a region and click the ID of the target VBR.
4.  Click the **BGP Peers** tab page, and then click **Create BGP Peer**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21437/154272711012050_en-US.png)

5.  Configure the BGP peer, and then click **OK**.

    |Configuration|Description|
    |:------------|:----------|
    |**BGP Group**|BGP group to which you want to add the BGP peer|
    |**BGP peer IP Address**|IP address of the BGP peer|


## Step 3: Add the BGP CIDR block {#section_lbw_wzx_dfb .section}

After configuring the BGP peer, you need to add the CIDR block of the local IDC.

To add the CIDR block of the local IDC, perform the following steps:

1.  Log on to the [Express Connect](https://partners-intl.console.aliyun.com/#/ri) console.
2.  In the left-side navigation pane, click **Physical Connections** \> **Virtual Border Routers \(VBRs\)**.
3.  Select a region and click the ID of the target VBR.
4.  Click the **BGP CIDR Blocks** tab, and then click **Add BGP CIDR Block**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21437/154272711012051_en-US.png)

5.  Enter the CIDR block to be added, and then click **OK**.

