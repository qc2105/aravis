doc_ignore_headers = [
	'arvenumtypes.h',
	'arvconfig.h',
	'arvbufferprivate.h',
	'arvchunkparserprivate.h',
	'arvinterfaceprivate.h',
	'arvdeviceprivate.h',
	'arvstreamprivate.h',
	'arvgvstreamprivate.h',
	'arvgvinterfaceprivate.h',
	'arvgvdeviceprivate.h',
	'arvvvstreamprivate.h',
	'arvuvinterfaceprivate.h',
	'arvuvdeviceprivate.h',
	'arvuvstreamprivate.h',
	'arvfakeinterfaceprivate.h',
	'arvfakedeviceprivate.h',
	'arvfakestreamprivate.h',
	'arvrealtimeprivate.h',
	'arvwakeupprivate.h',
	'arv.h'
]

if not enable_usb
	doc_ignore_headers += [
		'arvuvinterface.h',
		'arvuvdevice.h',
		'arvuvstream.h'
	]
endif

gnome.gtkdoc ('aravis',
	      main_xml: 'aravis-docs.xml',
	      src_dir: [join_paths (meson.source_root (), 'src'),
	                join_paths (meson.build_root (), 'src')],
	      gobject_typesfile: 'aravis.types',
	      dependencies: [aravis_library_dependencies],
	      scan_args: ['--ignore-headers=' + ' '.join (doc_ignore_headers), '--rebuild-types'],
	      content_files: ['aravis-overview.xml',
	      		      'aravis-gv.xml',
			      '../../../tests/arvexample.c',
			      '../../../tests/arvchunkparsertest.c'],
	      install_dir: 'aravis-@0@'.format (aravis_api_version),
	      install: true)
