FROM jover/php-base
LABEL maintainer="Joost Vermeulen <joost@jover.net>" \
      original_maintainer="Malitta Nanayakkara <malitta@gmail.com>"

RUN apt-get update && apt-get install -y \
	php-mcrypt \	
	php-mbstring

RUN	phpenmod mbstring