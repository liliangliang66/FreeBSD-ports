# $FreeBSD$

PORTNAME=	veloren
DISTVERSIONPREFIX=	v
DISTVERSION=	0.7.0
PORTREVISION=	1
CATEGORIES=	games
MASTER_SITES=	https://veloren.net/icons/favicon/:icon
DISTFILES=	android-icon-192x192.png:icon
EXTRACT_ONLY=	${DISTFILES:N*\:icon:C/:.*//}

MAINTAINER=	jbeich@FreeBSD.org
COMMENT=	Multiplayer voxel RPG written in Rust

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libasound.so:audio/alsa-lib
RUN_DEPENDS=	${LOCALBASE}/lib/alsa-lib/libasound_module_pcm_oss.so:audio/alsa-plugins

USES=		cargo gnome python:3.4+,build xorg
USE_GNOME=	gtk30
USE_XORG=	xcb
USE_GITHUB=	nodefault
GH_TUPLE=	zesterer:euc:c9a7c17a03d45fce00caeeca09afa1e1558cd183:euc \
		Imberflur:guillotiere:42c298f5bcf0f95f1a004360d05e25ca3711e9ed:guillotiere \
		bekker:msgbox-rs:68fe39a60019b38a1569ae4e9ed796a0f0542673:msgbox \
		xMAC94x:portpicker-rs:9d6df36c53c94684080a64a7212dd6bfc3617ee4:portpicker \
		amethyst:specs:7a2e348ab2223818bad487695c66c43db88050a5:specs \
		Imberflur:winit:e98133adf2abbfc4368f6c069d0beb2b8b688b42:winit
USE_GITLAB=	yes
GL_COMMIT=	8f8b20c9139fbe1ddfb1937e3264e592d42f4fd0
GL_TUPLE=	veloren:auth:b943c85e4a38f5ec60cd18c34c73097640162bfe:authcommon \
		veloren:conrod:1ab6eccf94b16a8977a3274b31d4dbfef9cf9a30:conrod_core \
		veloren:specs-idvs:fcb0b2306b571f62f9f85d89e79e087454d95efd:specsidvs
INSTALLS_ICONS=	yes
PLIST_FILES=	bin/${PORTNAME}-chat-cli \
		bin/${PORTNAME}-server-cli \
		bin/${PORTNAME}-voxygen \
		share/icons/hicolor/192x192/apps/${PORTNAME}.png
PORTDATA=	*

.if exists(/usr/bin/ld.lld) && ${/usr/bin/ld:L:tA} != /usr/bin/ld.lld
# veloren_voxygen*rcgu* has 71718 section headers, breaking old GNU ld.bfd in base
LDFLAGS+=	-fuse-ld=lld
.endif

DESKTOP_ENTRIES="Veloren (client)" \
		"" \
		"${PORTNAME}" \
		"${PORTNAME}-voxygen" \
		"Game;RolePlaying;" \
		""

CARGO_CRATES=	addr2line-0.12.1 \
		adler32-1.0.4 \
		ahash-0.3.8 \
		aho-corasick-0.7.10 \
		alsa-sys-0.1.2 \
		andrew-0.2.1 \
		android_glue-0.2.3 \
		android_log-sys-0.1.2 \
		ansi_term-0.11.0 \
		anymap-0.12.1 \
		approx-0.3.2 \
		arr_macro-0.1.3 \
		arr_macro_impl-0.1.3 \
		arraygen-0.1.13 \
		arrayref-0.3.6 \
		arrayvec-0.4.12 \
		arrayvec-0.5.1 \
		ascii-1.0.0 \
		async-std-1.5.0 \
		async-task-1.3.1 \
		atk-sys-0.6.0 \
		atom-0.3.5 \
		atty-0.2.14 \
		autocfg-0.1.7 \
		autocfg-1.0.0 \
		backtrace-0.3.48 \
		base-x-0.2.6 \
		base64-0.11.0 \
		base64-0.12.1 \
		bincode-1.2.1 \
		bindgen-0.53.3 \
		bitflags-1.2.1 \
		bitvec-0.17.4 \
		blake2b_simd-0.5.10 \
		block-0.1.6 \
		broadcaster-1.0.0 \
		bstr-0.2.13 \
		bumpalo-3.4.0 \
		byteorder-0.5.3 \
		byteorder-1.3.4 \
		bytes-0.4.12 \
		c_vec-1.3.3 \
		cairo-rs-0.4.1 \
		cairo-sys-rs-0.6.0 \
		calloop-0.4.4 \
		cast-0.2.3 \
		cc-1.0.54 \
		cexpr-0.4.0 \
		cfg-if-0.1.10 \
		cgl-0.3.2 \
		chrono-0.4.11 \
		chunked_transfer-1.2.0 \
		clang-sys-0.29.3 \
		clap-2.33.1 \
		clipboard-win-2.2.0 \
		cloudabi-0.0.3 \
		cocoa-0.19.1 \
		cocoa-0.20.2 \
		const-random-0.1.8 \
		const-random-macro-0.1.8 \
		const-tweaker-0.3.1 \
		const-tweaker-attribute-0.5.0 \
		constant_time_eq-0.1.5 \
		cookie-0.12.0 \
		copypasta-0.6.3 \
		core-foundation-0.6.4 \
		core-foundation-0.7.0 \
		core-foundation-sys-0.6.2 \
		core-foundation-sys-0.7.0 \
		core-graphics-0.17.3 \
		core-graphics-0.19.2 \
		core-video-sys-0.1.4 \
		coreaudio-rs-0.9.1 \
		coreaudio-sys-0.2.4 \
		cpal-0.11.0 \
		crc32fast-1.2.0 \
		criterion-0.3.2 \
		criterion-plot-0.4.2 \
		crossbeam-0.7.2 \
		crossbeam-channel-0.3.9 \
		crossbeam-channel-0.4.2 \
		crossbeam-deque-0.7.3 \
		crossbeam-epoch-0.7.2 \
		crossbeam-epoch-0.8.2 \
		crossbeam-queue-0.1.2 \
		crossbeam-queue-0.2.3 \
		crossbeam-utils-0.6.6 \
		crossbeam-utils-0.7.2 \
		csv-1.1.3 \
		csv-core-0.1.10 \
		ctor-0.1.15 \
		daggy-0.5.0 \
		darling-0.10.2 \
		darling_core-0.10.2 \
		darling_macro-0.10.2 \
		dashmap-3.11.4 \
		data-encoding-2.2.1 \
		deflate-0.7.20 \
		derivative-2.1.1 \
		deunicode-1.1.1 \
		diesel-1.4.5 \
		diesel_derives-1.4.1 \
		diesel_migrations-1.4.0 \
		directories-next-1.0.1 \
		dirs-sys-next-0.1.0 \
		discard-1.0.4 \
		dispatch-0.1.4 \
		dispatch-0.2.0 \
		dlib-0.4.2 \
		dot_vox-4.1.0 \
		dotenv-0.15.0 \
		downcast-rs-1.1.1 \
		draw_state-0.8.0 \
		either-1.5.3 \
		enum-iterator-0.6.0 \
		enum-iterator-derive-0.6.0 \
		error-chain-0.12.2 \
		euclid-0.19.9 \
		euclid_macros-0.1.0 \
		failure-0.1.8 \
		failure_derive-0.1.8 \
		filetime-0.2.10 \
		find_folder-0.3.0 \
		fixedbitset-0.1.9 \
		fnv-1.0.7 \
		foreign-types-0.3.2 \
		foreign-types-shared-0.1.1 \
		fsevent-2.0.2 \
		fsevent-sys-3.0.2 \
		fuchsia-cprng-0.1.1 \
		fuchsia-zircon-0.3.3 \
		fuchsia-zircon-sys-0.3.3 \
		futures-0.1.29 \
		futures-0.3.5 \
		futures-channel-0.3.5 \
		futures-core-0.3.5 \
		futures-cpupool-0.1.8 \
		futures-executor-0.3.5 \
		futures-io-0.3.5 \
		futures-macro-0.3.5 \
		futures-sink-0.3.5 \
		futures-task-0.3.5 \
		futures-timer-2.0.2 \
		futures-util-0.3.5 \
		fxhash-0.2.1 \
		gdk-0.8.0 \
		gdk-pixbuf-0.4.0 \
		gdk-pixbuf-sys-0.6.0 \
		gdk-sys-0.6.0 \
		getrandom-0.1.14 \
		gfx-0.18.2 \
		gfx_core-0.9.2 \
		gfx_device_gl-0.16.2 \
		gfx_gl-0.6.1 \
		gilrs-0.7.4 \
		gilrs-core-0.2.6 \
		gimli-0.21.0 \
		gio-0.4.1 \
		gio-sys-0.6.0 \
		git2-0.13.6 \
		gl_generator-0.13.1 \
		gl_generator-0.14.0 \
		glib-0.5.0 \
		glib-sys-0.6.0 \
		glob-0.3.0 \
		glsl-include-0.3.1 \
		glutin-0.24.1 \
		glutin_egl_sys-0.1.4 \
		glutin_emscripten_sys-0.1.1 \
		glutin_gles2_sys-0.1.4 \
		glutin_glx_sys-0.1.6 \
		glutin_wgl_sys-0.1.4 \
		gobject-sys-0.6.0 \
		gtk-0.4.1 \
		gtk-sys-0.6.0 \
		h2-0.1.26 \
		hashbrown-0.7.2 \
		heck-0.3.1 \
		hermit-abi-0.1.13 \
		hex-0.3.2 \
		hibitset-0.6.3 \
		horrorshow-0.8.3 \
		hound-3.4.0 \
		http-0.1.21 \
		http-body-0.1.0 \
		http-service-0.4.0 \
		http-service-hyper-0.4.1 \
		httparse-1.3.4 \
		hyper-0.12.35 \
		ident_case-1.0.1 \
		idna-0.1.5 \
		idna-0.2.0 \
		image-0.22.5 \
		indexmap-1.4.0 \
		inflate-0.4.5 \
		inotify-0.8.3 \
		inotify-sys-0.1.3 \
		instant-0.1.4 \
		io-kit-sys-0.1.0 \
		iovec-0.1.4 \
		itertools-0.9.0 \
		itoa-0.4.5 \
		jni-sys-0.3.0 \
		jobserver-0.1.21 \
		js-sys-0.3.40 \
		kernel32-sys-0.2.2 \
		khronos_api-3.1.0 \
		kv-log-macro-1.0.6 \
		lazy_static-1.4.0 \
		lazycell-1.2.1 \
		lewton-0.10.1 \
		libc-0.2.71 \
		libgit2-sys-0.12.7+1.0.0 \
		libloading-0.5.2 \
		libloading-0.6.2 \
		libsqlite3-sys-0.18.0 \
		libssh2-sys-0.2.17 \
		libudev-sys-0.1.4 \
		libz-sys-1.0.25 \
		line_drawing-0.7.0 \
		linked-hash-map-0.5.3 \
		lock_api-0.3.4 \
		log-0.4.8 \
		lz4-compress-0.1.1 \
		mach-0.2.3 \
		malloc_buf-0.0.6 \
		matchers-0.0.1 \
		matches-0.1.8 \
		maybe-uninit-2.0.0 \
		memchr-2.3.3 \
		memmap-0.7.0 \
		memoffset-0.5.4 \
		migrations_internals-1.4.1 \
		migrations_macros-1.4.2 \
		mime-0.3.16 \
		minifb-0.14.0 \
		mio-0.6.22 \
		mio-extras-2.0.6 \
		mio-uds-0.6.8 \
		miow-0.2.1 \
		mopa-0.2.2 \
		ndk-0.1.0 \
		ndk-glue-0.1.0 \
		ndk-sys-0.1.0 \
		net2-0.2.34 \
		nix-0.14.1 \
		nix-0.15.0 \
		nodrop-0.1.14 \
		noise-0.6.0 \
		nom-4.2.3 \
		nom-5.1.1 \
		notify-5.0.0-pre.3 \
		num-0.1.42 \
		num-0.2.1 \
		num-bigint-0.2.6 \
		num-complex-0.2.4 \
		num-integer-0.1.43 \
		num-iter-0.1.41 \
		num-rational-0.2.4 \
		num-traits-0.2.12 \
		num_cpus-1.13.0 \
		num_enum-0.4.3 \
		num_enum_derive-0.4.3 \
		objc-0.2.7 \
		objc-foundation-0.1.1 \
		objc_id-0.1.1 \
		object-0.19.0 \
		ogg-0.7.0 \
		old_school_gfx_glutin_ext-0.24.0 \
		once_cell-1.4.0 \
		oorandom-11.1.1 \
		openssl-probe-0.1.2 \
		openssl-sys-0.9.58 \
		orbclient-0.3.27 \
		ordered-float-1.0.2 \
		osmesa-sys-0.1.2 \
		packed_simd-0.3.3 \
		pango-0.4.0 \
		pango-sys-0.6.0 \
		parking_lot-0.9.0 \
		parking_lot-0.10.2 \
		parking_lot_core-0.6.2 \
		parking_lot_core-0.7.2 \
		peeking_take_while-0.1.2 \
		percent-encoding-1.0.1 \
		percent-encoding-2.1.0 \
		petgraph-0.4.13 \
		pin-project-0.4.20 \
		pin-project-internal-0.4.20 \
		pin-project-lite-0.1.7 \
		pin-utils-0.1.0 \
		piston-float-0.3.0 \
		piston-viewport-0.5.0 \
		pistoncore-input-0.24.0 \
		pkg-config-0.3.17 \
		plotters-0.2.15 \
		png-0.15.3 \
		ppv-lite86-0.2.8 \
		proc-macro-crate-0.1.5 \
		proc-macro-error-0.4.12 \
		proc-macro-error-1.0.4 \
		proc-macro-error-attr-0.4.12 \
		proc-macro-error-attr-1.0.4 \
		proc-macro-hack-0.5.16 \
		proc-macro-nested-0.1.5 \
		proc-macro2-0.4.30 \
		proc-macro2-1.0.18 \
		prometheus-0.9.0 \
		qstring-0.7.2 \
		quick-error-1.2.3 \
		quote-0.6.13 \
		quote-1.0.7 \
		radium-0.3.0 \
		rand-0.5.6 \
		rand-0.6.5 \
		rand-0.7.3 \
		rand_chacha-0.1.1 \
		rand_chacha-0.2.2 \
		rand_core-0.3.1 \
		rand_core-0.4.2 \
		rand_core-0.5.1 \
		rand_hc-0.1.0 \
		rand_hc-0.2.0 \
		rand_isaac-0.1.1 \
		rand_jitter-0.1.4 \
		rand_os-0.1.3 \
		rand_pcg-0.1.2 \
		rand_pcg-0.2.1 \
		rand_xorshift-0.1.1 \
		raw-window-handle-0.3.3 \
		rayon-1.3.0 \
		rayon-core-1.7.0 \
		rdrand-0.4.0 \
		redox_syscall-0.1.56 \
		redox_users-0.3.4 \
		regex-1.3.9 \
		regex-automata-0.1.9 \
		regex-syntax-0.6.18 \
		ring-0.16.14 \
		rodio-0.11.0 \
		ron-0.6.0 \
		roots-0.0.5 \
		route-recognizer-0.1.13 \
		rust-argon2-0.7.0 \
		rust-argon2-0.8.2 \
		rustc-demangle-0.1.16 \
		rustc-hash-1.1.0 \
		rustc_version-0.2.3 \
		rustls-0.17.0 \
		rusttype-0.7.9 \
		rusttype-0.8.3 \
		rusty-xinput-1.2.0 \
		ryu-1.0.5 \
		same-file-1.0.6 \
		scan_fmt-0.2.5 \
		scopeguard-1.1.0 \
		sct-0.6.0 \
		sdl2-0.32.2 \
		sdl2-sys-0.32.6 \
		semver-0.9.0 \
		semver-parser-0.7.0 \
		serde-1.0.114 \
		serde_derive-1.0.114 \
		serde_json-1.0.55 \
		serde_qs-0.5.2 \
		sha1-0.6.0 \
		sharded-slab-0.0.9 \
		shared_library-0.1.9 \
		shlex-0.1.1 \
		shred-0.10.2 \
		shred-derive-0.6.2 \
		shrev-1.1.1 \
		slab-0.4.2 \
		smallvec-0.6.13 \
		smallvec-1.4.0 \
		smithay-client-toolkit-0.6.6 \
		smithay-clipboard-0.4.0 \
		spin-0.5.2 \
		static_assertions-1.1.0 \
		stb_truetype-0.3.1 \
		stdweb-0.1.3 \
		stdweb-0.4.20 \
		stdweb-derive-0.5.3 \
		stdweb-internal-macros-0.2.9 \
		stdweb-internal-runtime-0.1.5 \
		string-0.2.1 \
		strsim-0.8.0 \
		strsim-0.9.3 \
		structopt-0.3.16 \
		structopt-derive-0.4.9 \
		sum_type-0.2.0 \
		svg_fmt-0.2.1 \
		syn-0.15.44 \
		syn-1.0.33 \
		syn-mid-0.5.0 \
		synstructure-0.12.4 \
		textwrap-0.11.0 \
		thiserror-1.0.20 \
		thiserror-impl-1.0.20 \
		thread_local-1.0.1 \
		tide-0.6.0 \
		time-0.1.43 \
		tiny_http-0.7.0 \
		tinytemplate-1.1.0 \
		tinyvec-0.3.3 \
		tokio-0.1.22 \
		tokio-buf-0.1.1 \
		tokio-current-thread-0.1.7 \
		tokio-executor-0.1.10 \
		tokio-io-0.1.13 \
		tokio-reactor-0.1.12 \
		tokio-sync-0.1.8 \
		tokio-tcp-0.1.4 \
		tokio-threadpool-0.1.18 \
		tokio-timer-0.2.13 \
		toml-0.5.6 \
		tracing-0.1.15 \
		tracing-appender-0.1.0 \
		tracing-attributes-0.1.8 \
		tracing-core-0.1.10 \
		tracing-futures-0.2.4 \
		tracing-log-0.1.1 \
		tracing-serde-0.1.1 \
		tracing-subscriber-0.2.6 \
		treeculler-0.1.0 \
		try-lock-0.2.2 \
		tuple_utils-0.3.0 \
		tynm-0.1.4 \
		unicode-bidi-0.3.4 \
		unicode-normalization-0.1.12 \
		unicode-segmentation-1.6.0 \
		unicode-width-0.1.7 \
		unicode-xid-0.1.0 \
		unicode-xid-0.2.0 \
		untrusted-0.7.1 \
		ureq-1.3.0 \
		url-1.7.2 \
		url-2.1.1 \
		uuid-0.8.1 \
		uvth-3.1.1 \
		uvth-4.0.1 \
		vcpkg-0.2.10 \
		vec_map-0.8.2 \
		vek-0.11.2 \
		version_check-0.1.5 \
		version_check-0.9.2 \
		void-1.0.2 \
		walkdir-2.3.1 \
		want-0.2.0 \
		wasi-0.9.0+wasi-snapshot-preview1 \
		wasm-bindgen-0.2.63 \
		wasm-bindgen-backend-0.2.63 \
		wasm-bindgen-macro-0.2.63 \
		wasm-bindgen-macro-support-0.2.63 \
		wasm-bindgen-shared-0.2.63 \
		wayland-client-0.23.6 \
		wayland-commons-0.23.6 \
		wayland-protocols-0.23.6 \
		wayland-scanner-0.23.6 \
		wayland-sys-0.23.6 \
		web-sys-0.3.40 \
		webpki-0.21.3 \
		webpki-roots-0.19.0 \
		winapi-0.2.8 \
		winapi-0.3.8 \
		winapi-build-0.1.1 \
		winapi-i686-pc-windows-gnu-0.4.0 \
		winapi-util-0.1.5 \
		winapi-x86_64-pc-windows-gnu-0.4.0 \
		winres-0.1.11 \
		ws2_32-sys-0.2.1 \
		x11-clipboard-0.5.1 \
		x11-dl-2.18.5 \
		xcb-0.9.0 \
		xdg-2.2.0 \
		xml-rs-0.8.3
CARGO_USE_GITHUB=	yes
CARGO_USE_GITLAB=	yes
CARGO_GIT_SUBDIR=	authcommon:authc:authc \
			conrod_core:conrod_core:conrod_core \
			conrod_core:conrod_winit:backends/conrod_winit
# https://gitlab.com/veloren/veloren/issues/264
CARGO_ENV=		RUSTC_BOOTSTRAP=1
# XXX https://github.com/rust-lang/cargo/issues/4101
CARGO_INSTALL_PATH=	chat-cli server-cli voxygen

post-patch:
# .git/ directory is missing, so don't abort if git binary is also missing
	@${REINPLACE_CMD} -e 's/"git"/"${TRUE}"/' \
		${WRKSRC}/common/build.rs
# Extract (snapshot) version from the port instead of empty file
	@${REINPLACE_CMD} -e '/GIT_HASH/s/=.*/= "${DISTVERSIONFULL}";/' \
		-e "/GIT_DATE/s/=.*/= \"$$(date -r $$(${AWK} '/TIMESTAMP/ { print $$3 }' \
			${DISTINFO_FILE}) +'%Y-%m-%d-%H:%M')\";/" \
		${WRKSRC}/common/src/util/mod.rs
# Respect PREFIX != /usr/local for system assets
	@${REINPLACE_CMD} -e 's,/usr/share,${DATADIR:H},' \
		${WRKSRC}/common/src/assets/mod.rs
# lang/python3 cannot be used as a dependency
	@${REINPLACE_CMD} -e 's/"python3"/"${PYTHON_CMD:T}"/' \
		${WRKSRC}/cargo-crates/xcb-*/build.rs

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/*
	(cd ${WRKSRC} && ${COPYTREE_SHARE} assets ${STAGEDIR}${DATADIR})
	${MKDIR} ${STAGEDIR}${PREFIX}/share/icons/hicolor/192x192/apps
	${INSTALL_DATA} ${DISTDIR}/android-icon-192x192.png \
		${STAGEDIR}${PREFIX}/share/icons/hicolor/192x192/apps/${PORTNAME}.png

.include <bsd.port.mk>
