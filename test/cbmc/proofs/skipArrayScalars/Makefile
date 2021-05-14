# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0

HARNESS_FILE=skipArrayScalars_harness
PROOF_UID=skipArrayScalars

# This value was experimentally chosen to provide 100% coverage
# without tripping unwinding assertions and without exhausting memory.
# This comes from the original skipCollection proof
CBMC_MAX_BUFSIZE=8

CHECK_FUNCTION_CONTRACTS += skipArrayScalars
USE_FUNCTION_CONTRACTS += skipString
USE_FUNCTION_CONTRACTS += skipAnyLiteral
USE_FUNCTION_CONTRACTS += skipNumber
USE_FUNCTION_CONTRACTS += skipSpaceAndComma

DEFINES += -DJSON_MAX_DEPTH="( $(CBMC_MAX_BUFSIZE) - 2 )"

UNWINDSET += __CPROVER_contracts_original_skipArrayScalars.0:$(CBMC_MAX_BUFSIZE)

include ../Makefile-json.common

# Substitution command to pass to sed for patching core_json.c. The
# characters " and # must be escaped with backslash.
CORE_JSON_SED_EXPR = s/^static //
