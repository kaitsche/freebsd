devd -- device state change daemon

Check interface down:

    notify 0 {
        match "system"                   "IFNET";
        match "subsystem"                "(xn0|xn1|xn2)";
        match "type"                     "LINK_DOWN";
        action "logger -p kern.err -t IFNET '$subsystem is DOWN'";
    };
