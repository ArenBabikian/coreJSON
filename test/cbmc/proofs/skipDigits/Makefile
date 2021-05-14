# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0

HARNESS_FILE=skipDigits_harness
PROOF_UID=skipDigits

# This value was experimentally chosen to provide 100% coverage
# without tripping unwinding assertions and without exhausting memory.

# this value comes from the old skipNumbers proof
CBMC_MAX_BUFSIZE=12

CHECK_FUNCTION_CONTRACTS += skipDigits

UNWINDSET += __CPROVER_contracts_original_skipDigits.0:$(CBMC_MAX_BUFSIZE)

include ../Makefile-json.common

# Substitution command to pass to sed for patching core_json.c. The
# characters " and # must be escaped with backslash.
CORE_JSON_SED_EXPR = s/^static //
