h_root_sources_public = [
  'attribute.h',
  'attributedeclaration.h',
  'attributenode.h',
  'document.h',
  'dtd.h',
  'keepblanks.h',
  'noncopyable.h',
  'relaxngschema.h',
  'schemabase.h',
  'xsdschema.h']
h_exceptions_sources_public = [
  join_paths('exceptions','exception.h'),
  join_paths('exceptions','parse_error.h'),
  join_paths('exceptions','validity_error.h'),
  join_paths('exceptions','internal_error.h'),
  join_paths('exceptions','wrapped_exception.h')]
h_io_sources_public = [
  join_paths('io','istreamparserinputbuffer.h'),
  join_paths('io','outputbuffer.h'),
  join_paths('io','ostreamoutputbuffer.h'),
  join_paths('io','parserinputbuffer.h')]
h_nodes_sources_public = [
  join_paths('nodes','cdatanode.h'),
  join_paths('nodes','commentnode.h'),
  join_paths('nodes','contentnode.h'),
  join_paths('nodes','element.h'),
  join_paths('nodes','entitydeclaration.h'),
  join_paths('nodes','entityreference.h'),
  join_paths('nodes','node.h'),
  join_paths('nodes','processinginstructionnode.h'),
  join_paths('nodes','textnode.h'),
  join_paths('nodes','xincludeend.h'),
  join_paths('nodes','xincludestart.h')]
h_parsers_sources_public = [
  join_paths('parsers','parser.h'),
  join_paths('parsers','saxparser.h'),
  join_paths('parsers','domparser.h'),
  join_paths('parsers','textreader.h')]
h_validators_sources_public = [
  join_paths('validators','dtdvalidator.h'),
  join_paths('validators','relaxngvalidator.h'),
  join_paths('validators','schemavalidatorbase.h'),
  join_paths('validators','validator.h'),
  join_paths('validators','xsdvalidator.h')]

h_sources_public = ['libxml++.h'] + h_root_sources_public + h_exceptions_sources_public + h_io_sources_public + h_parsers_sources_public + h_validators_sources_public

install_headers('libxml++.h', h_root_sources_public, subdir: 'libxml++')
install_headers(h_exceptions_sources_public, subdir: join_paths('libxml++', 'exceptions'))
install_headers(h_io_sources_public, subdir: join_paths('libxml++', 'io'))
install_headers(h_parsers_sources_public, subdir: join_paths('libxml++', 'parsers'))
install_headers(h_validators_sources_public, subdir: join_paths('libxml++', 'validators'))

cc_sources = [
  'attribute.cc',
  'attributedeclaration.cc',
  'attributenode.cc',
  'document.cc',
  'dtd.cc',
  'keepblanks.cc',
  'noncopyable.cc',
  'relaxngschema.cc',
  'schemabase.cc',
  'xsdschema.cc',
  join_paths('exceptions','exception.cc'),
  join_paths('exceptions','parse_error.cc'),
  join_paths('exceptions','validity_error.cc'),
  join_paths('exceptions','internal_error.cc'),
  join_paths('exceptions','wrapped_exception.cc'),
  join_paths('io','istreamparserinputbuffer.cc'),
  join_paths('io','outputbuffer.cc'),
  join_paths('io','ostreamoutputbuffer.cc'),
  join_paths('io','parserinputbuffer.cc'),
  join_paths('nodes','cdatanode.cc'),
  join_paths('nodes','commentnode.cc'),
  join_paths('nodes','contentnode.cc'),
  join_paths('nodes','element.cc'),
  join_paths('nodes','entitydeclaration.cc'),
  join_paths('nodes','entityreference.cc'),
  join_paths('nodes','node.cc'),
  join_paths('nodes','processinginstructionnode.cc'),
  join_paths('nodes','textnode.cc'),
  join_paths('nodes','xincludeend.cc'),
  join_paths('nodes','xincludestart.cc'),
  join_paths('parsers','parser.cc'),
  join_paths('parsers','saxparser.cc'),
  join_paths('parsers','domparser.cc'),
  join_paths('parsers','textreader.cc'),
  join_paths('validators','dtdvalidator.cc'),
  join_paths('validators','relaxngvalidator.cc'),
  join_paths('validators','schemavalidatorbase.cc'),
  join_paths('validators','validator.cc'),
  join_paths('validators','xsdvalidator.cc')]

glibmm_dep = dependency('glibmm-2.4')
libxml_dep = dependency('libxml-2.0', fallback: ['libxml2', 'xml2lib_dep'])

libxmlpp_lib = library('xml++', cc_sources,
		       soversion: libxmlpp_soversion,
		       version: libxmlpp_version,
		       include_directories: toplevel_inc,
		       dependencies: [glibmm_dep, libxml_dep],
		       install: true)
libxmlpp_dep = declare_dependency(link_with: libxmlpp_lib,
				  include_directories: [toplevel_inc, include_directories('.')],
				  dependencies: [glibmm_dep, libxml_dep])
