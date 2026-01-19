---
title: Content Modal
excerpt: Content Modal
deprecated: false
hidden: false
icon: far fa-arrows-maximize
link:
  new_tab: false
metadata:
  robots: index
---
> 📘 Info
>
> **Bold inside callout**
> **Bold inside callout**
> test
> test

<HTMLBlock>{`

`}</HTMLBlock>

<br />

| API       | Quota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `stream`  | Each `appId` has a quota for total stream layer throughput. Quotas are byte-rate thresholds. A single `appId` can span multiple producer and consumer instances, and the quota will apply for all of them as a single entity. For example, if the `appId` ”test-client” has a produce quota of 10200 KBps, this is shared across all instances with that same `appId`. The default quota per Kafka topic partition is: <br /> <br /> • Input throughput ("producer_byte_rate"): 10200 KBps <br /> • Output throughput rate ("consumer_byte_rate"): 2000 KBps |
| `index`   | The `index` API uses a resource-based throttling mechanism. When requests cause CPU and memory resources to exceed certain threshold, further requests are throttled while the system allocates more resources using autoscaling.                                                                                                                                                                                                                                                                                                                            |
| `publish` | The `publish` API has a quota of 5000 requests per minute, per `appId`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

| Column A                                 | Column B                    | Column C                |
| ---------------------------------------- | --------------------------- | ----------------------- |
| Line 1<br />Line 2<br />Line 3           | Alpha<br />Beta<br />Gamma  | One<br />Two<br />Three |
| Top<br /><br />Bottom (blank line above) | First<br />Second           | A<br />B<br />C         |
| Single line                              | Has a break<br />right here | Ends with break<br />   |

<Tabs>
  <Tab title="First Tab">
    Welcome to the content that you can only see inside the first Tab.
  </Tab>

  <Tab title="Second Tab">
    Here's content that's only inside the second Tab.
  </Tab>

  <Tab title="Third Tab">
    Here's content that's only inside the third Tab.
  </Tab>
</Tabs>

<Tabs>
  <Tab title="First Tab">
    Welcome to the content that you can only see inside the first Tab.
  </Tab>

  <Tab title="Second Tab">
    Here's content that's only inside the second Tab.
  </Tab>

  <Tab title="Third Tab">
    Here's content that's only inside the third Tab.
  </Tab>
</Tabs>

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        test
      </th>

      <th>
        test
      </th>

      <th>
        test
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Test

        * test
        * test
        * test
      </td>

      <td>
        _ITALIC_
      </td>

      <td>
        **BOLD**
      </td>
    </tr>

    <tr>
      <td>
        Here is `code`
      </td>

      <td>
        test
      </td>

      <td>
        test
      </td>
    </tr>
  </tbody>
</Table>

<br />
