# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0

HARNESS_FILE=skipString_harness
PROOF_UID=skipString

# This value was experimentally chosen to provide 100% coverage
# without tripping unwinding assertions and without exhausting memory.
CBMC_MAX_BUFSIZE=14

# time is reduced from ~90 seconds to 2-3 seconds
CHECK_FUNCTION_CONTRACTS += skipString
USE_FUNCTION_CONTRACTS += skipEscape
USE_FUNCTION_CONTRACTS += skipUTF8

UNWINDSET += __CPROVER_contracts_original_skipString.0:$(CBMC_MAX_BUFSIZE)
UNWINDSET += skipString.0:$(CBMC_MAX_BUFSIZE)
# UNWINDSET += skipEscape.0:$(CBMC_MAX_BUFSIZE)
# UNWINDSET += skipUTF8.0:$(CBMC_MAX_BUFSIZE)

# PROOF_SOURCES += $(PROOF_STUB)/skipGeneric.c
# PROOF_SOURCES += $(PROOF_STUB)/skipEscape.c
# PROOF_SOURCES += $(PROOF_STUB)/skipUTF8.c

include ../Makefile-json.common

# Substitution command to pass to sed for patching core_json.c. The
# characters " and # must be escaped with backslash.
CORE_JSON_SED_EXPR = s/^static //
# CORE_JSON_SED_EXPR = 1s/^/\#include \"core_json_annex.h\" /; s/^static //; s/bool skipUTF8\b/&_/
