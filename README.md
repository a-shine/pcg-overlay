# CS347 coursework

## Background

Building a custom overlay on top of the [a-shine/butter](https://github.com/a-shine/butter) framework (unstructured p2p application framework) focused on implementing group based persistent data management techniques to improve fault-tolerance (specifically information availability) on high churn networks.

## Try demo
To try a demo of the PCG persistent storage management overlay in action:
1. Make sure to have Go (1.17) installed
2. Clone the repository
3. Run the demo CLI program with:
    ```bash
    go run demo.go
    ```
4. Now start several nodes in different terminal instances, try adding and retrieving information from the various nodes. Watch as information persists beyond the existence of any single node.

**A good demo walk-through**:
1. Start a node in one terminal instance with `go run demo.go`
2. Start another node in another terminal instance with the same command
3. Add a piece of information to the first node with using the CLI interface
4. Retrieve the information from the second node with the CLI interface
5. Kill the first node with `ctrl-c` in the first terminal instance
   - **Note**: Ignore the `dial tcp 192.168.0.23:41991: connect: connection refused` log message - it is a non-fatal log generated by the Butter framework to indicate that a known host has become unreachable (it disappears once the known host list is updated)
6. Retry to retrieve the information from the second node - observe that the information has persisted beyond the existence of the node responsible for adding it