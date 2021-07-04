# Priority of Forces
The forces applied by different Magic functions have differing priorities. If a force with a higher priority is applied to an object at the same time as a force with a lower priority, the lower priority force will be ignored. The basic priority order of movement forces from highest to lowest is as follows:

1. [`Magic:Fling`](../../api/magic/Fling/) (with duration > 0)
2. `Magic:SetVelocity`
3. `Magic:Translate`
4. `Magic:SetAnchored`
5. `Magic:Follow`

The priority order of rotational forces is as follows:

1. `Magic:Spin`
2. `Magic:Watch`
3. `Magic:PointTowards`
4. `Magic:SetAnchored`

If two forces of the same priority are applied at the same time as each other by different players, it is handled differently depending on the force. Forces that charge mana with a subscription (like `Magic:SetVelocity` and `Magic:Watch`) will establish a middle-ground between the conflicting instructions, calculating an average value to use. Forces with instantaneous costs are overridden by the player who used it last.