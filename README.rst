discord.py
==========

.. image:: https://img.shields.io/pypi/v/snakecord.svg
   :target: https://pypi.python.org/pypi/snakecord
   :alt: PyPI version info
.. image:: https://img.shields.io/pypi/pyversions/snakecord.svg
   :target: https://pypi.python.org/pypi/snakecord
   :alt: PyPI supported Python versions

A modern, easy to use, feature-rich, and async ready API wrapper for Discord written in Python.

Key Features
-------------

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- Optimised in both speed and memory.

Installing
----------

**Python 3.8 or higher is required**

To install the library without full voice support, you can just run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U snakecord

    # Windows
    py -3 -m pip install -U snakecord

Otherwise to get voice support you should run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U "snakecord[voice]"

    # Windows
    py -3 -m pip install -U snakecord[voice]


To install the development version, do the following:

.. code:: sh

    $ git clone https://github.com/SnakecordDev/snakecord
    $ cd discord.py
    $ python3 -m pip install -U .[voice]


Optional Packages
~~~~~~~~~~~~~~~~~~

* `PyNaCl <https://pypi.org/project/PyNaCl/>`__ (for voice support)

Please note that when installing voice support on Linux, you must install the following packages via your favourite package manager (e.g. ``apt``, ``dnf``, etc) before running the above commands:

* libffi-dev (or ``libffi-devel`` on some systems)
* python-dev (e.g. ``python3.8-dev`` for Python 3.8)

Quick Example
--------------

.. code:: py

    import snakecord

    class MyClient(snakecord.Client):
        async def on_ready(self):
            print('Logged on as', self.user)

        async def on_message(self, message):
            # don't respond to ourselves
            if message.author == self.user:
                return

            if message.content == 'ping':
                await message.channel.send('pong')

    intents = snakecord.Intents.default()
    intents.message_content = True
    client = MyClient(intents=intents)
    client.run('token')

Bot Example
~~~~~~~~~~~~~

.. code:: py

    import snakecord
    from snakecord.ext import commands

    intents = snakecord.Intents.default()
    intents.message_content = True
    bot = commands.Bot(command_prefix='>', intents=intents)

    @bot.command()
    async def ping(ctx):
        await ctx.send('pong')

    bot.run('token')

You can find more examples in the examples directory.

Links
------

- `Documentation <https://snakecord.readthedocs.io/en/latest/index.html>`_
- `Discord API <https://discord.gg/discord-api>`_
