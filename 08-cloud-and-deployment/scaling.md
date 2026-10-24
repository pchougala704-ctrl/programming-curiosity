# Scaling

Scaling means adjusting a system's capacity as its workload changes. A small application may handle a few users on one machine; a popular service may need more computing power, storage, or network capacity.

**Vertical scaling** adds resources to one machine, such as more memory or faster processors. **Horizontal scaling** adds more machines or instances. Horizontal scaling can improve capacity and resilience, but often requires coordination, load balancing, and careful handling of shared state.

Before scaling, measure where the bottleneck is. Slow database queries, large files, or inefficient code may be the real cause. Caching and better indexes can sometimes help more than adding machines.

## Challenge questions

- **93.** What changes when one million users use an application?
- **94.** Why can't we simply buy one huge computer?
- **99.** How do large services handle millions of users?

Read the [seven-lens answers](./challenge-answers.md#cloud-and-deployment-seven-lens-answers).

The [rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers) explains how millions of people can use one application at the same time.

### Related rabbit-hole question

**How can millions of people use the same application at the same time?**

Read the [seven-lens rabbit-hole answer](../10-rabbit-holes/challenge-answers.md#rabbit-holes-seven-lens-answers).
