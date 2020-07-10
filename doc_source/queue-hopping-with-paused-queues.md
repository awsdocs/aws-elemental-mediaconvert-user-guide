# Queue hopping behavior with paused queues<a name="queue-hopping-with-paused-queues"></a>

Jobs don't hop from a queue while it's paused, but they hop freely to paused queues\.

## Hopping from a paused queue<a name="hopping-from-a-paused-queue"></a>

Jobs don't hop from a queue while it's paused\. Queue hopping behavior depends on how long the queue is paused\. Consider these two situations: 

**You submit a job to a queue and then pause the queue for longer than the queue hopping wait time\.**  
In this situation, whether the job hops depends on where the job is in the queue\. If there are any jobs ahead of it in the queue, the job hops to the destination queue\. If there are no jobs ahead of it in the queue, MediaConvert processes without hopping

For example, say that you submit a job to `Queue1` with a wait time of 15 minutes and a destination of `Queue2`\. Five minutes after you submit the job, you pause `Queue1`\. Ten minutes later, the job remains in `Queue1`\. Half an hour after that, you activate `Queue1`\. At that time, there are no jobs ahead of it in `Queue1`, so the job runs from `Queue1`\.

**You submit a job to a queue\. You pause the queue and then reactivate it before the wait time passes\.**  
In this situation, the time that the queue is paused doesn't affect queue hopping at all\.

For example, say that you submit a job to `Queue1` with a wait time of 15 minutes and a destination of `Queue2`\. Five minutes after you submit the job, you pause `Queue1`\. One minute later, you reactivate `Queue1`\. Nine minutes later \(15 minutes after you submitted the job\), there are still jobs ahead of it in the queue, so the job hops to `Queue2`, just as if you hadn't paused the queue\.

## Hopping to a paused queue<a name="hopping-to-a-paused-queue"></a>

Jobs hop freely from active queues to paused queues\. For example, say that you submit a job to `Queue1` with a wait time of 15 minutes and a destination of `Queue2`\. Five minutes after you submit the job, you pause `Queue2`\. Ten minutes later \(15 minutes after you submit the job\), the job hops to `Queue2` and remains there, waiting until you activate the queue\.