<!--
* Copyright (c) 2021, 2021 IBM Corp. and others
*
* This program and the accompanying materials are made
* available under the terms of the Eclipse Public License 2.0
* which accompanies this distribution and is available at
* https://www.eclipse.org/legal/epl-2.0/ or the Apache
* License, Version 2.0 which accompanies this distribution and
* is available at https://www.apache.org/licenses/LICENSE-2.0.
*
* This Source Code may also be made available under the
* following Secondary Licenses when the conditions for such
* availability set forth in the Eclipse Public License, v. 2.0
* are satisfied: GNU General Public License, version 2 with
* the GNU Classpath Exception [1] and GNU General Public
* License, version 2 with the OpenJDK Assembly Exception [2].
*
* [1] https://www.gnu.org/software/classpath/license.html
* [2] http://openjdk.java.net/legal/assembly-exception.html
*
* SPDX-License-Identifier: EPL-2.0 OR Apache-2.0 OR GPL-2.0 WITH
* Classpath-exception-2.0 OR LicenseRef-GPL-2.0 WITH Assembly-exception
-->

# -XX:\[+|-\]JITServerShareROMClasses

This option enables the server to share cached ROM classes between clients.

## Syntax

        -XX:[+|-]JITServerShareROMClasses

| Setting                 | Effect | Default                                                                            |
|-------------------------|--------|:----------------------------------------------------------------------------------:|
|`-XX:+JITServerShareROMClasses`           | Enable |                                                                                    |
|`-XX:-JITServerShareROMClasses`           | Disable| :fontawesome-solid-check:{: .yes aria-hidden="true"}<span class="sr-only">yes</span> |

## Explanation

This option should be enabled when multiple clients executing identical or similar applications connect to a single server.

This option enables a caching optimization that allows the server to use ROM classes cached
for one client while compiling for a different client. This reduces the amount of network communication between the server and the clients required, improving
startup time and reducing clients' CPU usage. Moreover, footprint at the server can be reduced because only a single copy for a particular Java class is cached.

<!-- ==== END OF TOPIC ==== xxjitservershareromclasses.md ==== -->