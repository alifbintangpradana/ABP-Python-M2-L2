import discord
from discord.ext import commands
import os
import random

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

# Dan inilah cara Kamu mengganti nama file dari variabel!

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Hi! I am a bot {bot.user}!')

organik = ["daun","sayur","kulit pisang", "ranting", "kayu"]
anorganik = ["plastik","besi","kabel", "karton", "kardus"]

@bot.command()
async def pilih(ctx, sampah):
    if sampah in organik:
        await ctx.send("Masukkan dalam sampah organik")
    elif sampah in anorganik:
        await ctx.send("Masukkan dalam sampah anorganik")

bot.run("TOKEN")
