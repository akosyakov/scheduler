## Probot: Scheduler

[![npm](https://img.shields.io/npm/v/probot-scheduler.svg)](https://www.npmjs.com/package/probot-scheduler)

A [Probot](https://github.com/probot/probot) extension to trigger events on an hourly schedule.

## Usage

```shell
$ npm install probot-scheduler
```

```js
const createScheduler = require('probot-scheduler')

module.exports = (robot) => {
  createScheduler(robot)
  robot.on('schedule.repository', context => {
    // this event is triggered on an interval, which is 1 hr by default
  })
}
```

## Configuration

There are a few environment variables that can change the behavior of the scheduler:

- `DISABLE_DELAY=true` - Perform the schedule immediately on startup, instead of waiting for the random delay between 0 and 59:59 for each repository, which exists to avoid all schedules being performed at the same time.

- `IGNORED_ACCOUNTS=comma,separated,list` - GitHub usernames to ignore when scheduling. These are typically spammy or abusive accounts.
