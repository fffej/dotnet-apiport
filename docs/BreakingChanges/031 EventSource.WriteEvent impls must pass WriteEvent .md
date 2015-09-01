## 31: EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)

### Scope
Minor

### Version Introduced
4.5.1

### Change Description
The runtime now enforces the contract that specifies the following: A class derived from EventSource that defines an ETW event method must call the base class EventSource.WriteEvent method with the event ID followed by the same arguments that the ETW event method was passed. 

- [ ] Quirked
- [ ] Build-time break
- [x] Source analyzer available

### Recommended Action
An IndexOutOfRangeException exception is thrown if an EventListener reads EventSource data in process for an event source that violates this contract. 

### Affected APIs
* Not detectable via API analysis

[More information](https://msdn.microsoft.com/en-us/library/dn458360(v=vs.110).aspx)