# Rendering

Ever wonder why `react` is separated from `ReacDOM`, well this is actually because `react` library is only responsible for the diffing, while `ReactDOM` is responsible for the DOM part, so `react` actually doesn't know that you are generating HTML, that's why React and React native can work, both use react for the diffing but both use different things to render, one render mobile components while the other manipulate HTML stuff.

### Useful Links

- [CrossComm Talk](https://www.youtube.com/watch?v=i793Qm6kv3U)
