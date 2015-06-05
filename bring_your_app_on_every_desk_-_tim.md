# Bring Your App on Every Desk - Tim

Auerswald is a manufacturer of deskphones running Android as operating systems. The devices cover the full range from an entry model (perfect to bring Android really on every desk) which is available for less than 150 euro over a mid-range model to an executive version. In our session we invited the participants to stage for an open discussion.

The question was, what can you do with an Android deskphone and what is required to be successful. While mobile smartphones address every potential user (from the school kid to the executive) the usage of a deskphone has more of business angle. The discussion had two major discussion points, one was to identify use-case-scenarios and integrated in this discussion was how to do it, which API’s and possibilities does Auerswald offer to get everything working?

## Use-cases aka What does it mean to replace your dumb phone on your desk with a smart phone?

Beside the standard scenarios like synchronized address book (Exchange, Google, etc.) and Calendar there were several other smart scenarios to talk about, which really show the power of smart devices compared to closed boxes normal phones and PBX’s usually are. The power of API enables to integrate EASILY and cost efficient functionality.

In the group we found following useful scenarios:

**CRM integration**, have an App to identify incoming callers, is it an important client or just the customer who is not paying his bills. Show up notes about the customer. After the call, the app could write back that there was a conversation with this specific customer.

**Call Center scenarios**, for inbound call centers the agent could immediately identify for which client the call is. Relevant information can be pushed directly to the display. For outbound calls the dialing can be made really easy. The call plan could be integrated into an app, the physical buttons on the phone could be offered to enter multiple choice (yes/no) answers by the client.

**Call a cab widget**, would ease the life of secretaries to call a cab, one press and the widget shows the secretary the time until the cab arrives.

**Nagios monitoring over buttons**, an administrator in the group brought up the scenario in which the multicolor buttons could show server/network status. It’s immediately visible when the status changes from green to yellow or even red. A button press could retrieve exactly the affected system.

**Fleet control**, another similar scenario to monitor the status of a fleet of trucks, delivery drivers, etc. With one glimpse of an eye the scheduler can see and react to delays or incidents.

 

## How to get things going:

Auerswald uses a standard Android open source package and only extended the stock Android where needed. Auerswalds intention is to document and offer all required API’s and interfaces for developers to access every part of the device. While the SIP-phone app (from Auerswald) uses standard phone API’s, and the keypad (0,1,2,3,4,5,6,7,8,9,*,’) use standard input mechanisms, the phones also have additional function keys with tri-color LED (green, yellow, red) and different states (on, off, blinking) which are not available on other Android devices. To gain access to these keys, Auerswald implemented an API, with which a button could be assigned to a specific app. This API is documented on the website:

[www.auerswald.de](http://www.auerswald.de/de/service/125-developer-service/1447-developer-mass-provisioning-comfortel-2600ip.html)

The website also covers additional information about APP provisioning, software updates in closed networks and central manageability.

## Housekeeping

While most interfaces already rely on Android standards and may be used, the formfactor of the phones required some modifications. The largest modification is around audio processing, while the standard audio path through Android is not optimized for low latency, Auerswald implemented its own audio path with echo canceler and different audio optimizations for phone scenarios. Currently the engineers work in enabling apps to gain access to these technologies so that Apps can benefit from this low latency and phone optimized audio.

 

## Conclusion:

We were happy to figure out potential use cases and hope that companies and App developers see the potential our devices have to offer. We are looking forward to see the ideas and possibilities come true. If you require further assistance, please reach out to us at: [developer@auerswald.de](mailto:developer@auerswald.de)
