# NICE IEX Spoke

## Description

IEX is a [NICE](https://www.nice.com/engage/workforce-optimization/workforce-management) Workforce Management solution. Included in this integration is a set of actions usable in Flow Designer to access or import agent data from IEX. The actions make use of a central script include 'IEX' to route SOAP calls.

![NICE IEX Spoke](https://raw.githubusercontent.com/platform-experience/api-integration-library/master/src/ap-nice-iex-spoke/images/ap-nice-iex-spoke.png)

## Additional Information/Notes

![NICE IEX Spoke](https://raw.githubusercontent.com/platform-experience/api-integration-library/master/src/ap-nice-iex-spoke/images/ap-nice-iex-spoke-actions.png)

### Available Actions

* **Get Activity Codes** outputs all activity data in a JSON string.
* **Get MUs** outputs all MU data.
* **Get Schedule Data** outputs schedule data for selected user.<sup>\*</sup>
* **Get Skills Data** outputs current skills for selected user.<sup>\*</sup>
* **Import Schedule from IEX** gets schedule data for selected user, then creates a new `cmn_schedule` with returned entries.<sup>\*\*</sup>

<sup>\*</sup> By default, date range is set to current week, assigned in flow action script.

<sup>\*\*</sup> By default, schedule is made a child of 'Testing Schedule'. This can be switched to associate with the assigned user, by removing the `true` value passed to `importAgentsSchedules` in flow action script.

## Installation

Download and install update set **[ap-nice-iex-spoke.u-update-set.xml](https://github.com/platform-experience/api-integration-library/blob/master/src/ap-nice-iex-spoke/ap-nice-iex-spoke.u-update-set.xml)**

* SN Product Documentation - ['Load a customization from a single XML file'](https://docs.servicenow.com/bundle/kingston-application-development/page/build/system-update-sets/task/t_SaveAnUpdateSetAsAnXMLFile.html)

## Configuration

> None
