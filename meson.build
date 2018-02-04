project('Catch2', 'cpp', version: '2.1.1', license: 'boost')

test_sources = [
  'projects/SelfTest/TestMain.cpp'
, 'projects/SelfTest/IntrospectiveTests/CmdLine.tests.cpp'
, 'projects/SelfTest/IntrospectiveTests/PartTracker.tests.cpp'
, 'projects/SelfTest/IntrospectiveTests/TagAlias.tests.cpp'
, 'projects/SelfTest/IntrospectiveTests/String.tests.cpp'
, 'projects/SelfTest/IntrospectiveTests/Xml.tests.cpp'
, 'projects/SelfTest/UsageTests/Approx.tests.cpp'
, 'projects/SelfTest/UsageTests/BDD.tests.cpp'
, 'projects/SelfTest/UsageTests/Benchmark.tests.cpp'
, 'projects/SelfTest/UsageTests/Class.tests.cpp'
, 'projects/SelfTest/UsageTests/Compilation.tests.cpp'
, 'projects/SelfTest/UsageTests/Condition.tests.cpp'
, 'projects/SelfTest/UsageTests/Decomposition.tests.cpp'
, 'projects/SelfTest/UsageTests/EnumToString.tests.cpp'
, 'projects/SelfTest/UsageTests/Exception.tests.cpp'
, 'projects/SelfTest/UsageTests/Message.tests.cpp'
, 'projects/SelfTest/UsageTests/Misc.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringChrono.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringGeneral.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringPair.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringTuple.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringVector.tests.cpp'
, 'projects/SelfTest/UsageTests/ToStringWhich.tests.cpp'
, 'projects/SelfTest/UsageTests/Tricky.tests.cpp'
, 'projects/SelfTest/UsageTests/VariadicMacros.tests.cpp'
]

surrogate_sources = [
  'projects/SelfTest/SurrogateCpps/catch_console_colour.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_debugger.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_interfaces_reporter.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_option.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_stream.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_test_case_tracker.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_test_spec.cpp'
, 'projects/SelfTest/SurrogateCpps/catch_xmlwriter.cpp'
]

impl_sources = [
  'include/internal/catch_approx.cpp'
, 'include/internal/catch_assertionhandler.cpp'
, 'include/internal/catch_assertionresult.cpp'
, 'include/internal/catch_benchmark.cpp'
, 'include/internal/catch_capture_matchers.cpp'
, 'include/internal/catch_commandline.cpp'
, 'include/internal/catch_common.cpp'
, 'include/internal/catch_config.cpp'
, 'include/internal/catch_console_colour.cpp'
, 'include/internal/catch_context.cpp'
, 'include/internal/catch_debug_console.cpp'
, 'include/internal/catch_debugger.cpp'
, 'include/internal/catch_decomposer.cpp'
, 'include/internal/catch_errno_guard.cpp'
, 'include/internal/catch_exception_translator_registry.cpp'
, 'include/internal/catch_fatal_condition.cpp'
, 'include/internal/catch_interfaces_capture.cpp'
, 'include/internal/catch_interfaces_config.cpp'
, 'include/internal/catch_interfaces_exception.cpp'
, 'include/internal/catch_interfaces_registry_hub.cpp'
, 'include/internal/catch_interfaces_runner.cpp'
, 'include/internal/catch_interfaces_testcase.cpp'
, 'include/internal/catch_list.cpp'
, 'include/internal/catch_leak_detector.cpp'
, 'include/internal/catch_matchers.cpp'
, 'include/internal/catch_matchers_floating.cpp'
, 'include/internal/catch_matchers_string.cpp'
, 'include/internal/catch_message.cpp'
, 'include/internal/catch_registry_hub.cpp'
, 'include/internal/catch_interfaces_reporter.cpp'
, 'include/internal/catch_random_number_generator.cpp'
, 'include/internal/catch_reporter_registry.cpp'
, 'include/internal/catch_result_type.cpp'
, 'include/internal/catch_run_context.cpp'
, 'include/internal/catch_section.cpp'
, 'include/internal/catch_section_info.cpp'
, 'include/internal/catch_session.cpp'
, 'include/internal/catch_startup_exception_registry.cpp'
, 'include/internal/catch_stream.cpp'
, 'include/internal/catch_stringref.cpp'
, 'include/internal/catch_string_manip.cpp'
, 'include/internal/catch_tag_alias.cpp'
, 'include/internal/catch_tag_alias_autoregistrar.cpp'
, 'include/internal/catch_tag_alias_registry.cpp'
, 'include/internal/catch_test_case_info.cpp'
, 'include/internal/catch_test_case_registry_impl.cpp'
, 'include/internal/catch_test_case_tracker.cpp'
, 'include/internal/catch_test_registry.cpp'
, 'include/internal/catch_test_spec.cpp'
, 'include/internal/catch_test_spec_parser.cpp'
, 'include/internal/catch_timer.cpp'
, 'include/internal/catch_tostring.cpp'
, 'include/internal/catch_totals.cpp'
, 'include/internal/catch_uncaught_exceptions.cpp'
, 'include/internal/catch_version.cpp'
, 'include/internal/catch_wildcard_pattern.cpp'
, 'include/internal/catch_xmlwriter.cpp'
]

reporter_sources = [
  'include/reporters/catch_reporter_bases.cpp'
, 'include/reporters/catch_reporter_compact.cpp'
, 'include/reporters/catch_reporter_console.cpp'
, 'include/reporters/catch_reporter_junit.cpp'
, 'include/reporters/catch_reporter_multi.cpp'
, 'include/reporters/catch_reporter_xml.cpp'
]

compiler = meson.get_compiler('cpp')
if compiler.get_id() == 'gcc' or compiler.get_id() == 'clang'
  args = [
    '-Wno-non-virtual-dtor'
  ]
else
  args = []
endif

include = include_directories('include')

test('tests'
, executable(
    'tests'
  , test_sources + surrogate_sources + impl_sources + reporter_sources
  , include_directories : include
  , implicit_include_directories : false
  , cpp_args: args
  )
)

catch_dep = declare_dependency(include_directories : include)